## Thales

A CLI tool to automatically generate and update README.md files using [ISO 639 language codes](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes) nomenclature by scanning project codebases. It also performs thorough code reviews, which highlight security vulnerabilities, performance bottlenecks, concurrency issues, and other potential problems.

> Created Thales to solve the inconvenience of manually updating README.md files and ensure code quality through automated reviews as codebases evolve.

### Getting Started

Follow these steps to set up and execute Thales:

1. **Installation**

Download the latest version of Thales for your operating system from the [releases page](https://github.com/0xnu/thales/releases).

Add Thales binaries for all OS/architectures and code review outputs to your `.gitignore` file:

```bash
# Thales Binaries
thales_*
*.zip

# Thales Code Review
code_reviews/
reviews/
custom_reviews/
*_review/
```

2. **Environment Setup**

Thales supports multiple LLMs. Set up the API key for your preferred model:

For Claude (default):
- Get your API key from [Anthropic's Claude Platform](https://www.merge.dev/blog/anthropic-api-key)

For OpenAI:
- Get your API key from the [OpenAI Platform Dashboard](https://www.merge.dev/blog/chatgpt-api-key)

For Grok-2:
- Get your API key from [xAI's Developer Portal](https://www.merge.dev/blog/grok-api-key)

For Mixtral:
- Get your API key from the [Mistral AI Platform](https://www.merge.dev/blog/mistral-ai-api-key)

Configure your environment variables with the following command:

```bash
export ANTHROPIC_API_KEY="enter_claude_api_key" && \
export OPENAI_API_KEY="enter_openai_api_key" && \
export GROK_API_KEY="enter_grok_api_key" && \
export MIXTRAL_API_KEY="enter_mixtral_api_key"
```

3. **Usage**

For MacOS:

```bash
# Documentation tasks
./thales_darwin_amd64 --new                          # New README with default settings
./thales_darwin_amd64 --update --lang es             # Update README in Spanish
./thales_darwin_amd64 --new --output docs/README.md  # Custom output location

# Code review
./thales_darwin_amd64 --cb . --llm claude            # Review codebase with Claude
./thales_darwin_amd64 --sf main.go --llm openai      # Review file with OpenAI
./thales_darwin_amd64 --cb . --llm grok2             # Review codebase with Grok-2
./thales_darwin_amd64 --cb . --llm mixtral           # Review codebase with Mixtral
./thales_darwin_amd64 --cb . --llm claude --focus security        # Security review with Claude
./thales_darwin_amd64 --cb . --llm openai --focus performance    # Performance review with OpenAI
./thales_darwin_amd64 --sf main.go --llm claude --severity high  # High-severity with Claude
./thales_darwin_amd64 --cb . --llm openai --focus all --severity medium  # All areas with OpenAI

# Advanced options
./thales_darwin_amd64 --list-languages               # List supported languages
./thales_darwin_amd64 --llm openai                   # Use OpenAI instead of Claude
./thales_darwin_amd64 --review-output reports        # Custom review output directory
./thales_darwin_amd64 --cb . --pdf                   # Review codebase with PDF output
./thales_darwin_amd64 --sf main.go --pdf             # Review single file with PDF output
./thales_darwin_amd64 --cb . --html                  # Review codebase with HTML output
./thales_darwin_amd64 --sf main.go --html            # Review single file with HTML output
```

For Linux:

```bash
# Documentation tasks
./thales_linux_amd64 --new                          # New README
./thales_linux_amd64 --update --lang pt             # Update in Portuguese
./thales_linux_amd64 --new --llm openai --lang it   # Use OpenAI, Italian output

# Code review
./thales_linux_amd64 --cb . --llm claude            # Full review with Claude
./thales_linux_amd64 --sf src/main.go --llm openai  # Single file with OpenAI
./thales_linux_amd64 --sf main.go --llm grok2       # Single file with Grok-2
./thales_linux_amd64 --cb . --llm mixtral           # Full review with Mixtral
./thales_linux_amd64 --cb . --llm claude --focus security,performance  # Multi-focus with Claude
./thales_linux_amd64 --sf lib/utils.go --llm openai --severity high   # Critical with OpenAI
./thales_linux_amd64 --cb . --llm claude --review-output custom_reviews  # Custom dir with Claude

# Advanced options
./thales_linux_amd64 --list-languages               # Available languages
./thales_linux_amd64 --llm claude                   # Specify LLM
./thales_linux_amd64 --cb . --pdf                   # Review codebase with PDF output
./thales_linux_amd64 --sf main.go --pdf             # Review single file with PDF output
./thales_linux_amd64 --cb . --html                  # Review codebase with HTML output
./thales_linux_amd64 --sf main.go --html            # Review single file with HTML output
```

For Windows:

```bash
# Documentation tasks
.\thales_windows_amd64.exe --new                    # Generate README
.\thales_windows_amd64.exe --update --lang zh       # Update in Chinese
.\thales_windows_amd64.exe --new --output docs\README.md  # Custom location

# Code review
.\thales_windows_amd64.exe --cb . --llm claude      # Review with Claude
.\thales_windows_amd64.exe --sf main.go --llm openai # Review with OpenAI
.\thales_windows_amd64.exe --cb . --llm grok2       # Review with Grok-2
.\thales_windows_amd64.exe --cb . --llm mixtral     # Review with Mixtral
.\thales_windows_amd64.exe --cb . --llm claude --focus security  # Security with Claude
.\thales_windows_amd64.exe --sf app.go --llm openai --severity medium  # Medium+ with OpenAI
.\thales_windows_amd64.exe --cb . --llm claude --focus all  # Full review with Claude

# Advanced options
.\thales_windows_amd64.exe --list-languages         # Show languages
.\thales_windows_amd64.exe --llm openai             # Use OpenAI
.\thales_windows_amd64.exe --review-output reviews  # Set review output
.\thales_windows_amd64.exe --cb . --pdf             # Review codebase with PDF output
.\thales_windows_amd64.exe --sf main.go --pdf       # Review single file with PDF output
.\thales_windows_amd64.exe --cb . --html            # Review codebase with HTML output
.\thales_windows_amd64.exe --sf main.go --html      # Review single file with HTML output
```

4. **Finish**

To unset the environment variables you set, you can use the following command:

```bash
unset ANTHROPIC_API_KEY && \
unset OPENAI_API_KEY && \
unset GROK_API_KEY && \
unset MIXTRAL_API_KEY
```

### License

This project is licensed under the BSD 3-Clause License - see the [LICENSE](LICENSE) file for details.

### Citation

```tex
@misc{thalesafo2025,
  author       = {Oketunji, A.F.},
  title        = {Thales},
  year         = 2025,
  version      = {1.0.8},
  publisher    = {Finbarrs Oketunji},
  doi          = {10.5281/zenodo.14994039},
  url          = {https://doi.org/10.5281/zenodo.14994039}
}
```

### Copyright

(c) 2025 Finbarrs Oketunji. All Rights Reserved.

> Thanks for all the emails! It is named after [Thales of Miletus](https://en.wikipedia.org/wiki/Thales_of_Miletus).