# ConchProtocol SDK

ConchProtocol is a source-free, end-to-end encryption SDK being prepared by
NOESIS Pixel Art Private Limited for application developers.

> **ConchProtocol Developer Preview is experimental cryptographic software. It has not completed an independent security audit and must not protect production communications.**

## Release status

No public SDK package or binary is available from this repository yet. There
are deliberately no installation commands or download links. The first planned
candidate is an Android-only `0.6.0-preview.1` Developer Preview, subject to the
license, security, package, runtime, documentation, and final human-approval
gates described in [Android release gates](docs/ANDROID-RELEASE-GATES.md).

| Platform | Public status |
| --- | --- |
| Android API 34+ | Preview preparation; not published |
| Apple iOS/macOS | Unavailable pending renewed binary-package acceptance |
| Browser | Unavailable pending renewed packaged-runtime acceptance |
| Linux desktop | Unavailable pending renewed Linux ARM64 package acceptance |
| Windows and other targets | Unavailable |

## Developer contracts

ConchProtocol does not replace application security architecture. Integrators
remain responsible for authenticated peer identity and continuity, protected
durable application transactions, account/device binding, transport, content
policy, and safe recovery. Remote owners require a separately authenticated,
durable, linearizable rollback anchor outside the client snapshot domain. Read
[host and anchor requirements](docs/HOST-AND-ANCHOR.md) before evaluating the SDK.

The public distribution will contain binary SDK packages, public API
documentation, notices, SBOMs, checksums, and verification records. It will not
contain the proprietary protocol implementation source, private fixtures,
credentials, internal provenance, test harnesses, or production service secrets.

## Documents

- [Supported-platform policy](docs/PLATFORMS.md)
- [Android integration boundary](docs/ANDROID.md)
- [Host and anchor requirements](docs/HOST-AND-ANCHOR.md)
- [Release verification](docs/RELEASE-VERIFICATION.md)
- [Legal status](docs/LEGAL-STATUS.md)
- [Security reporting](SECURITY.md)
- [Support policy](SUPPORT.md)
- [Changelog](CHANGELOG.md)

No license to download, use, or redistribute an SDK is granted by this
pre-release repository scaffold. The owner-approved public binary SDK license
will be added before any package is made available.
