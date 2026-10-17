# francora-github-actions

Zentrale, wiederverwendbare GitHub Actions und Workflows für Francora.

## Verwendungsbare Workflows

### Standard CI Pipeline (`ci-standard.yml`)

Ein universeller CI-Workflow zum Auschecken des Codes, Einrichten von Node.js, Installieren der Abhängigkeiten und Ausführen von Tests.

#### Einbindung in andere Repositories

Erstelle in deinem Ziel-Repository eine Datei unter `.github/workflows/ci.yml`:

```yaml
name: CI Pipeline

on:
  push:
    branches: [ "main", "develop" ]
  pull_request:
    branches: [ "main" ]

jobs:
  run-ci:
    uses: francora/francora-github-actions/.github/workflows/ci-standard.yml@main
    with:
      node-version: "20.x"
