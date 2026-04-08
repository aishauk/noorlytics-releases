# Noorlytics Tech AI

Noorlytics is a local-first CLI for analyzing technical debt, dependencies, and code quality using AI.

It runs locally with Ollama by default, so your code never leaves your machine.

#### Referrals
- Home page: [noorlytics.se](https://noorlytics.se)
- LinkedIn: [Noorlytics AI Tech](https://www.linkedin.com/company/noorlytics-ai-tech)

## Requirements
- macOS or Linux  
- Ollama  

## Quick Start (2–3 minutes)

### 1. Install Ollama

**macOS**

    brew install ollama

**Linux**

    curl -fsSL https://ollama.com/install.sh | sh

Start Ollama:

    ollama serve

Download a model (recommended):

    ollama pull mistral

---

### 2. Install Noorlytics

Download `noorlytics.zip` and unzip it.

You’ll get:

    noor
    
Make it executable and move it to your PATH:

    chmod +x noor
    sudo mv noor /usr/local/bin/noor

Verify:

    noor --help

---

### 3. Configure Noorlytics

Create config folder:

    mkdir -p ~/.noorlytics
    cp .env.sample ~/.noorlytics/.env

Edit `~/.noorlytics/.env`:

    NOOR_LICENSE_KEY=your-license-key
    NOOR_MODE=ollama
    NOOR_MODEL=mistral

---

### 4. Run your first analysis

Go to any codebase:

    cd your-project

Run:

    noor analyze .

Results will appear in:

    ./reports/

---

## Commands

Analyze code:

    noor analyze .

Analyze dependencies:

    noor analyze-deps requirements.txt

Get refactoring suggestions:

    noor suggest src/

Generate test stubs:

    noor add-tests src/

Check license:

    noor license-status

---

## Output

Reports are generated in:

    ./reports

Formats:
- Markdown (.md)
- JSON (.json)

Safe to commit.

---

## Configuration

Global config:

    ~/.noorlytics/.env

Project-specific (optional):

    ./.env

---

## Modes

Default (recommended):

    NOOR_MODE=ollama

Optional cloud mode:

    NOOR_MODE=openai
    OPENAI_API_KEY=your-key

---
## Local mode behavior

Noorlytics automatically adapts to your environment.

- Local mode prioritizes stability and privacy  
- Cloud mode prioritizes speed and deeper analysis  

If you're running locally, start with the default settings.

If an analysis times out, reducing output (`NOOR_ANALYZE_NUM_PREDICT`) is often more effective than increasing timeout.

See `/docs/local-mode.md` for tuning and advanced configuration.

---

## Why Noorlytics?

- Find technical debt faster
- Catch risky dependencies and licenses
- Generate actionable improvements
- Run fully offline

---

Built with care by Aisha Kujovic

[noorlytics.se](https://noorlytics.se)
