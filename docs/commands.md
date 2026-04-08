# Commands

Noorlytics is designed to be simple and predictable.

---

## Analyze a project

    noor analyze .

Scans your codebase for technical debt and issues.

---

## Analyze dependencies

    noor analyze-deps requirements.txt

Finds vulnerabilities and license risks.

---

## Suggest improvements

    noor suggest src/

Generates refactoring suggestions.

---

## Generate test stubs

    noor add-tests src/

Creates starting points for unit tests.

---

## Check license status

    noor license-status

Shows your current usage and license state.

---

## Output

All results are saved to:

    ./reports/

Formats:

- Markdown (.md)
- JSON (.json)
