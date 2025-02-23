## Thales

The CLI tool automatically generates and updates README.md files by scanning project codebases. It supports nomenclature for all [ISO 639 language codes](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes).

> Created Thales to solve the inconvenience of manually updating README.md files as codebases evolve.

### Getting Started

Follow these steps to set up and execute Thales:

1. **Installation**

Download the latest version of Thales for your operating system from the [releases page](https://github.com/0xnu/thales/releases).

Add Thales binaries for all OS/architectures to your .gitignore file:

```bash
# Thales Binaries
thales_*
*.zip
```

2. **Environment Setup**

[Grab an API Key](https://www.merge.dev/blog/anthropic-api-key) from your Anthropic account and set it as an environment variable:

```bash
export ANTHROPIC_API_KEY="enter_your_api_key"
```

3. **Usage**

For MacOS:

```bash
# List all supported languages
./thales_darwin_amd64 --list-languages

# Generate a new README in English (default)
./thales_darwin_amd64 --new

# Generate in Spanish
./thales_darwin_amd64 --new --lang es

# Custom output location with German language
./thales_darwin_amd64 --new --output docs/README.md --lang de

# Update existing README in French
./thales_darwin_amd64 --update --lang fr
```

For Linux:

```bash
# List available languages
./thales_linux_amd64 --list-languages

# Generate a new README
./thales_linux_amd64 --new --lang pt

# Update existing README
./thales_linux_amd64 --update --lang it
```

For Windows:

```bash
# View supported languages
./thales_windows_amd64.exe --list-languages

# Generate a new README
./thales_windows_amd64.exe --new --lang zh

# Update existing README
./thales_windows_amd64.exe --update --lang ja
```

4. **Finish**

To unset the environment variable you set, you can use the following command:

```bash
unset ANTHROPIC_API_KEY
```

### License

This project is licensed under the BSD 3-Clause License - see the [LICENSE](LICENSE) file for details.

### Citation

```tex
@misc{thalesafo2025,
  author       = {Oketunji, A.F.},
  title        = {Thales},
  year         = 2025,
  version      = {1.0.0},
  publisher    = {Finbarrs Oketunji},
  doi          = {10.5281/zenodo.14913280},
  url          = {https://doi.org/10.5281/zenodo.14913280}
}
```

### Copyright

(c) 2025 Finbarrs Oketunji. All Rights Reserved.