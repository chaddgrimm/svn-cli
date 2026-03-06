# svn-cli

Minimal Alpine-based Docker image for the Subversion (SVN) client. Use it as a drop-in replacement for the `svn` command without installing it locally.

## Usage

Add this alias to your shell config (`~/.zshrc` or `~/.bashrc`):

```bash
alias svn='docker run --rm -v "$PWD":/app -w /app YOUR_DOCKERHUB_USERNAME/svn'
```

Replace `YOUR_DOCKERHUB_USERNAME` with your Docker Hub username (e.g. `myuser/svn`).

Then run SVN commands as usual:

```bash
svn checkout https://example.com/repo/trunk
svn status
svn update
```

## Tags

Images are tagged by the SVN binary version:

- `latest` - always points to the newest build
- `1.14.5-cli` - full version (patch level)
- `1.14-cli` - minor version (floats to latest patch)

## Image size

~10-15 MB (Alpine Linux + Subversion only).
