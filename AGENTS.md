# AI / Coding Agent Installation and Recovery Guide

This file is intended for AI assistants (ChatGPT, Codex, Claude, Gemini, Copilot-style agents) helping a user install, migrate, repair, or adapt this repository.

## Primary rule

**Preserve user data before changing code or paths.** Do not delete or overwrite user data to make an installation appear clean.

## Project model

The system is a Windows desktop workflow for publishing anonymized whole-slide images.

Default Patoloji Pratik layout:

```text
E:\github             application + local state
E:\Pratik_slaytları   source WSI files
```

Central repository:

```text
patolojipratik/galeri
```

Per-slide repositories:

```text
gallery-001, gallery-002, ...
```

The central repository is both the web-gallery index and the public software-update channel. Published slide tiles live in per-slide repositories.

## Files/directories that are user state

Treat these as protected unless the user explicitly requests a recovery operation and a backup has been made:

```text
config/
data/
repos/
work/
logs/
E:\Pratik_slaytları\
```

Especially protect:

```text
data\slides.csv
config\settings.json
```

Never expose or print:

- GitHub personal access tokens
- Windows Credential Manager secrets
- the private update-signing key
- patient-identifying metadata

## Safe files to recreate

The Python virtual environment is machine-specific and can be recreated:

```text
.venv\
```

On migration to a new Windows computer, do not assume an existing `.venv` is portable. Rename/remove it only after confirming the application is closed, then run `KURULUM.bat` to recreate it.

## Runtime requirements

The application currently requires:

- Windows
- Python 3.10 or newer
- Git (`git.exe`); Git for Windows is the simplest supported installation, and GitHub Desktop's bundled Git may also be detected
- internet access for GitHub publishing

Python dependencies are installed from the application's `requirements.txt` by `KURULUM.bat`.

## Installation on a new computer with an intact SSD

Follow this order:

1. Inspect the SSD without modifying files.
2. Confirm the expected directories exist.
3. Prefer assigning the SSD drive letter `E:` if this is an existing Patoloji Pratik installation.
4. Install Python 3.10+ if missing.
5. Install Git for Windows if no usable `git.exe` exists.
6. Back up `data\slides.csv` and `config\settings.json`.
7. Rename the old `.venv` to `.venv_eski` (or remove it after backup if appropriate).
8. Run `KURULUM.bat`.
9. Run `BASLAT.bat`.
10. Only if publishing reports a missing token, ask the repository owner to run `GITHUB_BAGLA.bat` locally. Never ask the user to paste the token into chat.

## Drive-letter migration

For an existing Patoloji Pratik SSD, **prefer changing the SSD drive letter to `E:`** rather than rewriting persistent paths.

If `E:` cannot be used:

1. Back up `data\slides.csv` and `config\settings.json`.
2. Inspect `config\settings.json` for absolute paths using the old drive letter.
3. Inspect `data\slides.csv` for absolute source paths using the old drive letter.
4. Change only filesystem-path values that actually point to the moved SSD.
5. Preserve CSV quoting, encoding, row order, gallery IDs, diagnoses, titles and status fields.
6. Do not renumber `gallery-XXX` repositories.
7. Validate that source files resolve before allowing processing to start.
8. Start with a read-only/status check where possible before processing a new slide.

Do not blindly search-and-replace every `E:` string across the repository.

## SSD failure / recovery

If the original SSD failed:

1. Identify available backups before creating new state.
2. Restore `data\slides.csv`, `config\settings.json`, and source WSI files if available.
3. Published GitHub repositories can verify already-published slides, but GitHub is intentionally **not** a complete backup of local user state or source WSI files.
4. If `slides.csv` is missing, do not start from an empty inventory without reconciliation. Use central `slides.json`, published `gallery-XXX` repositories, and any local backups to reconstruct state deliberately.
5. Never delete published slide repositories merely because local state is incomplete.

## Update architecture

Canonical public update metadata:

```text
guncelleme/latest.json
```

A normal user runs:

```text
BASLAT.bat
```

which checks for updates before launching the application.

A maintainer publishes a new signed application package with:

```text
GUNCELLEME_YAYINLA.bat
```

Do not hand-edit `latest.json` unless performing a deliberate recovery and you fully understand the package SHA-256/signature relationship.

## Update security

Online update packages are verified using SHA-256 plus an Ed25519 signature. The private signing key must stay only with the maintainer and must never be committed to GitHub.

Do not replace `update_trusted_public.key` during a routine update. Key rotation is a separate trust-migration operation.

## GitHub API/token usage

No token is needed for:

- reading the public repository
- reading `guncelleme/latest.json`
- downloading a public update package
- local package verification

A token/API access is needed for operations such as:

- creating/updating repositories
- pushing slide/gallery content
- GitHub Actions/Pages management
- publishing a new application update from the maintainer workstation

Use the local credential mechanism already implemented by the project. Do not store secrets in source files.

## Publishing safeguards

Before any destructive operation:

- confirm the exact target repository
- confirm whether it is the central `galeri` repo or a per-slide `gallery-XXX` repo
- back up local state
- do not treat a transient GitHub Actions/Pages failure as a bad slide upload

Do not delete the central `galeri` repository.

## Adapting/forking for another organization

For an independent installation:

1. Use a separate GitHub account/organization.
2. Change `github_username`, `gallery_repo`, `repo_prefix`, source paths and update-manifest URL.
3. Create a new update-signing keypair with the provided key-generation tool.
4. Never reuse the Patoloji Pratik private signing key.
5. Use a new token scoped to the new account/repositories.
6. Review all branding and URLs before first publish.
7. Add an explicit software license if redistribution/reuse is intended.

## Documentation map

Read these before making changes:

```text
README.md                       public overview (TR + EN)
HARICI_SSD_DEVAM_REHBERI.md     end-user SSD migration/recovery guide (TR)
KENDI_SISTEMINI_KUR.md          independent adaptation guide (TR)
YONETICI_REHBERI_TR.md          Patoloji Pratik maintainer runbook (TR)
guncelleme/SURUM_NOTLARI.md     current release notes
```

When uncertain, prefer a reversible change, preserve existing IDs/data, and report what remains unverified.
