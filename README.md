# Zotero native Linux amd64 builder

This repository supplies an isolated native GitHub Actions build, cache and
verified package artifacts for Debian/Ubuntu amd64. It calls the shared
build workflow pinned at `f26ffb2d0af02f11736099ac84f5e3e849a9fd04` in
[openresearchtools/zotero-termux](https://github.com/openresearchtools/zotero-termux).
Application source, recipes, automation patches, component pins and licenses
live there. The updated Zotero application is built from source, using the
pinned official Mozilla Gecko runtime as upstream does. Termux/Bionic paths
and its socket-shortening compatibility library are not applied on Linux.

The shared workflow scans packaged native dependencies, installs its DEB with
APT without recommendations, checks the fresh-profile local API and Java/OXT
registration, and uploads artifacts only on success. The source repository
dispatches this builder and collects its source-matched package using the
existing `TERMUX` token: Actions read/write, Contents read and Metadata read.
No token or signing secret is installed in this builder. Releases and APT
publication are owned by the source repository, not this repository.

Run **Zotero native Linux amd64** with an exact source SHA and request ID.
Build artifacts remain available for 90 days. See the shared
[Linux instructions](https://github.com/openresearchtools/zotero-termux/blob/main/linux/README.md)
for dependency policy, installation, automation and publication.
