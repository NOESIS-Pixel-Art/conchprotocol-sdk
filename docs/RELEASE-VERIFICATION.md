# Release verification

No public artifacts exist yet. Verification commands and trusted signing-key
identifiers will be published only with the exact approved release.

Every future release page will provide:

- immutable package identity and version;
- source revision and source-to-artifact build record;
- complete package/archive member inventory;
- SHA-256 checksums and company-signed release statement;
- SPDX or CycloneDX SBOM and complete dependency/license notices;
- supported targets and exact compile/link/runtime evidence level;
- mandatory experimental/non-production warning for preview versions;
- independent specification review and named human release approval.

Consumers must verify publisher identity as well as file integrity. A checksum
copied from the same untrusted location as a package is not an independent trust
channel. Released bytes are never replaced under an existing version.
