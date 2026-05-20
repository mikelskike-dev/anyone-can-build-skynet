# Phase 2: 6-Layer Verification

Every critical finding goes through this pipeline:

## Layer 1 — File existence
`curl raw.githubusercontent.com/$repo/$branch/$path`
If 404 → discarded.

## Layer 2 — Content freshness
Verify the secret still exists in the current file across ALL branches.

## Layer 3 — Repo activity
Stars, forks, last push, releases. A repo untouched since 2015 gets lower priority.

## Layer 4 — Impact
How many people depend on this? Downloads, dependents, community size.

## Layer 5 — Live deployment
DNS resolution, GitHub Pages, CI/CD pipelines. Is there a live site behind this code?

## Layer 6 — Exploitability
- Is there a known exploit technique? (e.g., ViewState forgery)
- Is there a tool? (ysoserial.net, Metasploit)
- What's the CVSS?

## Verdict
Only findings that pass ALL 6 layers are reported as confirmed.
