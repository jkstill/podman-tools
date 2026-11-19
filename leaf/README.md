
# Leaf Runnner for leaf markdown viewer

leaf is a terminal markdown viewer that renders markdown to the terminal with colors and formatting. This repository contains a Dockerfile to build a container image for running leaf in a consistent environment.

## Rebuild leaf-runner image

podman build -f Dockerfile.leaf -t localhost/leaf-runner .


## From leaf README.md

https://github.com/rivolink/leaf

### Render to terminal with colors

`leaf --inline README.md`

### Force plain text, no ANSI codes (no colors)

`leaf --inline plain README.md`

# Force ANSI colors even when piping

`leaf --inline ansi README.md`

### Set a specific width

```bash
leaf --inline 60 README.md
leaf --inline ansi:60 README.md
```

### Pipe from stdin
`cat README.md | leaf --inline`

### Use as a fzf preview
```bash
fzf --preview 'leaf --inline ansi {}'
fzf --preview 'leaf --inline ansi:$FZF_PREVIEW_COLUMNS {}'
```

