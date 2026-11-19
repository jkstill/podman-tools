
FROM mcr.microsoft.com/dotnet/sdk:10.0-noble

ARG ILSPYCMD_VERSION=10.1.0.8386

RUN dotnet tool install ilspycmd \
      --tool-path /opt/ilspycmd \
      --version "${ILSPYCMD_VERSION}" \
    && ln -s /opt/ilspycmd/ilspycmd /usr/local/bin/ilspycmd \
    && /usr/local/bin/ilspycmd --version

WORKDIR /work

CMD ["/usr/local/bin/ilspycmd", "--help"]

