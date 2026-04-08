# Configuration

Noorlytics is configured using environment variables.

You can set them globally or per project.

---

## Global configuration

    ~/.noorlytics/.env

## Project-specific configuration (optional)

    ./.env

---

## Variables

### NOOR_LICENSE_KEY

Your license key used for authentication.

---

### NOOR_MODE

Controls where analysis runs.

- ollama (default, local)
- openai (cloud)

---

### NOOR_MODEL

Model used for analysis.

Example:

    mistral

---

### NOOR_HTTP_TIMEOUT

How long Noorlytics waits for a response from the model.

Higher values allow longer analyses.

---

### NOOR_ANALYZE_NUM_PREDICT

Controls how much output the model generates.

Lower values = faster, more concise output  
Higher values = more detailed output

---

## Recommended defaults

    NOOR_MODE=ollama
    NOOR_MODEL=mistral
    NOOR_HTTP_TIMEOUT=300
    NOOR_ANALYZE_NUM_PREDICT=160
