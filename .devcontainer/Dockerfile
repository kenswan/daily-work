FROM mcr.microsoft.com/devcontainers/dotnet:dev-10.0-noble

# The upstream image ships a Yarn apt source whose signing key has rotated,
# which causes `apt-get update` (run by features like docker-in-docker) to
# fail with: NO_PUBKEY 62D54FD4003F6525. Remove the stale source; Yarn can
# still be installed via the Node feature / corepack when needed.
RUN rm -f /etc/apt/sources.list.d/yarn.list \
 && rm -f /usr/share/keyrings/yarn-archive-keyring.gpg \
 && apt-get update
