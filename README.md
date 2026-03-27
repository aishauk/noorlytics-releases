# Noorlytics CLI

Noorlytics is a local-first CLI tool for analyzing technical debt, dependencies,
licenses, and structure in codebases.

It runs AI models locally on your machine using Ollama, with optional support
for OpenAI if you explicitly enable it.

Your source code stays on your computer.

--------------------------------------------------------------------

FEATURES

- Analyze source code for technical debt
- Dependency analysis:
  - risky or incompatible licenses
  - known security vulnerabilities
- AI-powered refactoring suggestions
- Unit test stub generation
- Markdown and JSON reports
- Local-first execution via Ollama
- Optional OpenAI support
- .env-based configuration

--------------------------------------------------------------------

REQUIREMENTS

Supported platforms:
- macOS
- Linux
- Windows (not supported yet)

Software:
- Local AI runtime: https://ollama.com/
- Optional: OpenAI API key (only if using OpenAI mode)

No Python, pip, or virtual environment is required.

--------------------------------------------------------------------

PACKAGE CONTENTS

After unzipping `noorlytics.zip`, you will find:

- noor
  The Noorlytics CLI binary.
  This is the only executable you need to run Noorlytics.

- README.md
  Documentation with installation, configuration, and usage instructions.

- .env.sample
  A sample environment configuration file.
  Copy this file to `~/.noorlytics/.env` and add your license key and settings.

- LICENSE
  License information for Noorlytics.

--------------------------------------------------------------------

INSTALLATION

1) Install Ollama

    brew install ollama
    ollama pull mistral

Any supported Ollama model can be used. Mistral is used as default.

--------------------------------------------------------------------

2) Install Noorlytics CLI

Download the file `noorlytics.zip` and unzip it.

Make the binary executable and place it in your PATH:

    chmod +x noor
    sudo mv noor /usr/local/bin/noor

Verify installation:

    noor --help

--------------------------------------------------------------------

CONFIGURATION (.env)

Noorlytics is configured using environment variables.

Global configuration (recommended):

    mkdir -p ~/.noorlytics
    cp .env.sample ~/.noorlytics/.env

Edit ~/.noorlytics/.env and add:

    NOOR_LICENSE_KEY=your-license-key
    NOOR_MODE=ollama

Project-specific configuration (optional):

Create a .env file in a project directory to override global settings.

--------------------------------------------------------------------

USAGE

Analyze a directory:

    noor analyze .

Analyze dependencies:

    noor analyze-deps requirements.txt

Generate refactoring suggestions:

    noor suggest src/

Generate unit test stubs:

    noor add-tests src/

Check license status (does not consume runs):

    noor license-status

--------------------------------------------------------------------

OUTPUT

- Reports are written to the reports directory
- Formats:
  - Markdown (.md)
  - JSON (.json)
- Safe to commit or share

--------------------------------------------------------------------

LOCAL-FIRST & COMPLIANCE

- When using Ollama, no source code is sent to external services
- Suitable for restricted or regulated environments
- OpenAI usage is fully opt-in and user-controlled

--------------------------------------------------------------------

ROADMAP

- CI integration
- Windows support

--------------------------------------------------------------------

Built with care by Aisha Ugljanin