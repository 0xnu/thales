## Thales

The CLI tool automatically generates and updates README.md files by scanning project codebases. It supports nomenclature for all [ISO 639 language codes](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes).

> Created Thales to solve the inconvenience of manually updating README.md files as codebases evolve.

### Getting Started

Follow these steps to set up and execute Thales:

1. **Installation**

Download the latest version of Thales for your operating system from the [releases page](https://github.com/0xnu/thales/releases). Add Thales binaries for all OS/architectures to your .gitignore file:

```bash
# Thales Binaries
thales_*
*.zip
```

2. **Environment Setup**

Thales supports both Claude and OpenAI. Set up the API key for your preferred LLM:

For Claude (default):

- [Get Claude API Key](https://www.merge.dev/blog/anthropic-api-key) from Anthropic

```bash
export ANTHROPIC_API_KEY="enter_your_api_key"
```

For OpenAI:

- [Get OpenAI API Key](https://www.merge.dev/blog/chatgpt-api-key) from OpenAI platform

```bash
export OPENAI_API_KEY="enter_your_api_key"
```

3. **Usage**

For MacOS:

```bash
# List all supported languages
./thales_darwin_amd64 --list-languages

# Generate a new README using Claude (default)
./thales_darwin_amd64 --new --llm claude

# Generate using OpenAI in Spanish
./thales_darwin_amd64 --new --llm openai --lang es

# Custom output with German language using Claude
./thales_darwin_amd64 --new --llm claude --output docs/README.md --lang de

# Update existing README using OpenAI in French
./thales_darwin_amd64 --update --llm openai --lang fr
```

For Linux:

```bash
# List available languages
./thales_linux_amd64 --list-languages

# Generate a new README using Claude
./thales_linux_amd64 --new --llm claude --lang pt

# Update existing README using OpenAI
./thales_linux_amd64 --update --llm openai --lang it
```

For Windows:

```bash
# View supported languages
./thales_windows_amd64.exe --list-languages

# Generate a new README using OpenAI
./thales_windows_amd64.exe --new --llm openai --lang zh

# Update existing README using Claude
./thales_windows_amd64.exe --update --llm claude --lang ja
```

4. **Finish**

To unset the environment variables you set, you can use the following command:

```bash
unset ANTHROPIC_API_KEY && unset OPENAI_API_KEY
```

### License

This project is licensed under the BSD 3-Clause License - see the [LICENSE](LICENSE) file for details.

### Citation

```tex
@misc{thalesafo2025,
  author       = {Oketunji, A.F.},
  title        = {Thales},
  year         = 2025,
  version      = {1.0.2},
  publisher    = {Finbarrs Oketunji},
  doi          = {10.5281/zenodo.14926342},
  url          = {https://doi.org/10.5281/zenodo.14926342}
}
```

### Copyright

(c) 2025 Finbarrs Oketunji. All Rights Reserved.