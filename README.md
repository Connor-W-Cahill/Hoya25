# Hoya25 — File Forensics & Metadata Analyzer

A file forensics and metadata analysis tool built at HoyaHacks 2025. Upload files to inspect metadata, detect corruption, and analyze image properties. SvelteKit frontend with a Python analysis backend.

## Architecture

```
app/              # Python backend — file analysis engine
  main.py         # Entry point — processes pending uploads
  reader.py       # File type detection and hex content extraction
  clock.py        # Timestamp/datetime extraction
  imager.py       # Image metadata (EXIF, dimensions, camera info)
  scheduler.py    # Upload queue management
  jsonifier.py    # Result formatting
  watcher.py      # File system watcher
  api.py          # REST API

hoya25/           # SvelteKit frontend
  src/            # Svelte components, routes, stores
  drizzle.config  # Database ORM config
  e2e/            # Playwright end-to-end tests
  .storybook/     # Component documentation
```

## Features

- Upload and analyze files (images, documents)
- Extract metadata: file type, size, timestamps, camera info, dimensions
- Detect file corruption via hex analysis
- Web UI for uploading and viewing results
- Internationalization support (inlang)

## Tech Stack

- **Frontend**: SvelteKit, TypeScript, Tailwind CSS, Drizzle ORM
- **Backend**: Python 3
- **Testing**: Playwright (E2E), Vitest (unit), Storybook
- **Build**: Vite

## Getting Started

### Backend

```bash
cd app
python main.py
```

### Frontend

```bash
cd hoya25
npm install
npm run dev
```
