# Build Instructions

This document provides instructions for building the Flutter documentation website.

## Prerequisites

The following tools are required to build the website:

1. **Node.js** (version 22.11.0 or later)
   - Download from [nodejs.org](https://nodejs.org/)
   - The repository includes a `.nvmrc` file for version management

2. **pnpm** (version 10.4.1 or later)
   - Install via corepack (recommended):
     ```bash
     corepack enable
     corepack install
     ```

3. **Dart SDK** (version 3.7 or later)
   - Download from [dart.dev](https://dart.dev/get-dart)
   - Or install Flutter which includes Dart

## Build Steps

Follow these steps to build the website:

### 1. Clone the repository with submodules

```bash
git clone --recurse-submodules https://github.com/flutter/website.git
cd website
```

If you've already cloned without submodules, run:

```bash
git submodule update --init --recursive
```

### 2. Install Dart dependencies

```bash
dart pub get
```

### 3. Install npm packages

```bash
pnpm install
```

### 4. Build the website

```bash
./dash_site build
```

The built website will be available in the `_site` directory.

## Build Output

After a successful build:
- The `_site` directory contains the complete static website
- Approximately 640 HTML pages are generated
- Total build size is approximately 289MB
- Build time is typically 30-45 seconds

## Development Server

To run a local development server with live reload:

```bash
./dash_site serve
```

This will start a local server at http://localhost:4000

## Additional Commands

The `dash_site` tool provides several useful commands:

- `./dash_site --help` - Show all available commands
- `./dash_site check-all` - Run all validation checks
- `./dash_site verify-firebase-json` - Verify Firebase configuration
- `./dash_site refresh-excerpts` - Update code excerpts
- `./dash_site analyze-dart` - Analyze Dart code
- `./dash_site test-dart` - Run Dart tests

## Troubleshooting

### Missing submodules
If you get errors about missing packages from `site-shared`, run:
```bash
git submodule update --init --recursive
```

### Node version issues
Ensure you have Node.js 22.11.0 or later:
```bash
node --version
```

### Dart version issues
Ensure you have Dart SDK 3.7 or later:
```bash
dart --version
```
