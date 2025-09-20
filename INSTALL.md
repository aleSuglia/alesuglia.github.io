# Install instructions

## Installing Hugo v0.136.5 on macOS (Apple Silicon)

This guide explains how to manually install Hugo v0.136.5 on a Mac with an M1/M2/M3 processor and prevent Homebrew from updating it. This is useful if you need a specific Hugo version for compatibility reasons.

### 0. Prerequisites
- Ensure you have [Homebrew](https://brew.sh/) and [Go](https://golang.org/dl/) installed.

### 1. Clone the Hugo Repository
Create a temporary directory and clone the Hugo source code for version `v0.136.5`:

```zsh
mkdir -p ~/tmp/hugo-build
cd ~/tmp/hugo-build
git clone --branch v0.136.5 --depth 1 https://github.com/gohugoio/hugo.git
cd hugo
```

### 2. Set Build Metadata
Retrieve the commit hash and current build date:

```zsh
COMMIT_HASH=$(git rev-parse HEAD)
BUILD_DATE=$(date -u +"%Y-%m-%dT%H:%M:%SZ")
```

### 3. Compile Hugo with Extended Features
Build Hugo with the necessary flags:

```zsh
go build -tags extended -ldflags "-s -w \
  -X github.com/gohugoio/hugo/common/hugo.commitHash=${COMMIT_HASH} \
  -X github.com/gohugoio/hugo/common/hugo.buildDate=${BUILD_DATE} \
  -X github.com/gohugoio/hugo/common/hugo.vendorInfo=brew" \
  -o hugo
```

### 4. Install the Compiled Binary
Move the compiled binary to `/opt/homebrew/bin/` and make it executable:

```zsh
sudo mv hugo /opt/homebrew/bin/hugo
chmod +x /opt/homebrew/bin/hugo
```

### 5. Verify the Installation
Check that Hugo is installed and running the correct version:

```zsh
hugo version
```

### 6. Clean Up
Remove the temporary build directory:

```zsh
rm -rf ~/tmp/hugo-build
```

---
Procedure adapted from [this gist](https://gist.github.com/peterwake/2851767e4424d11688d9a6f40149c3da).

