
# IlSpy Command-Line Interface

[ILSpy is the open-source, cross-platform .NET assembly browser and decompiler](https://github.com/icsharpcode/ilspy)

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

