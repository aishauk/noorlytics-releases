# Getting Started

Get Noorlytics up and running in a few minutes.

---

## 1. Install Ollama

macOS

    brew install ollama

Linux

    curl -fsSL https://ollama.com/install.sh | sh

Start Ollama:

    ollama serve

Download a model:

    ollama pull mistral

---

## 2. Install Noorlytics

Download and unzip `noorlytics.zip`.

Make the binary executable and move it to your PATH:

    chmod +x noor
    sudo mv noor /usr/local/bin/noor

Verify installation:

    noor --help

---

## 3. Configure Noorlytics

Create a config directory:

    mkdir -p ~/.noorlytics
    cp .env.sample ~/.noorlytics/.env

Edit:

    NOOR_LICENSE_KEY=your-license-key
    NOOR_MODE=ollama
    NOOR_MODEL=mistral

---

## 4. Run your first analysis

Navigate to your project:

    cd your-project

Run:

    noor analyze .

Reports will be generated in:

    ./reports/

---

Noorlytics is designed to run locally by default. No code leaves your machine.
