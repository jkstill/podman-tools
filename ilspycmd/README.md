
podman build -t ilspycmd .

podman run --rm ilspycmd

podman run --rm \
  -v "$PWD:/work:ro,z" \
  ilspycmd \
  /work/SomeLibrary.dll

## Decompile an entire assembly as a compilable project:

mkdir -p decompiled

podman run --rm \
  --userns=keep-id \
  -v "$PWD:/work:z" \
  ilspycmd \
  -p \
  -o /work/decompiled \
  /work/SomeLibrary.dll

