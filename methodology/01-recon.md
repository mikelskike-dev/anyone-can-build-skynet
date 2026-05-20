# Phase 1: Reconnaissance

## Objective
Map GitHub for critical CVEs and exposed credentials using only the public API — zero local downloads.

## Tool
GitHub Code Search API (authed with a PAT).

## Dork categories (200+ queries)

### AI/ML RCE
- `langflow exec validate/code`
- `langflow /api/v1/validate/code`
- `sglang pickle.loads 0.0.0.0`
- `open-webui OLLAMA_BASE_URL`
- `open-webui WEBUI_SECRET_KEY`

### Microsoft
- `validationKey= DECRYPTIONKEY= web.config`
- `machineKey validationKey web.config`
- `Add-SPSolution -LiteralPath`
- `CVE-2025-53770 SharePoint`

### Linux
- `sudo 1.9.14 apt-get`
- `sudo 1.9.15 Dockerfile`
- `copy_fail exploit kernel`
- `xfrm ipsec exploit`

### Supply chain
- `pull_request_target: write-all`
- `tj-actions/changed-files@`
- `GITHUB_TOKEN: write packages`

## Results
~1050 raw findings across 8 categories.
