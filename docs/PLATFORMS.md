# Supported-platform policy

Only targets present in an exact published package and backed by the stated
final-package evidence are supported. Package import, compilation, or the
presence of an architecture slice does not establish runtime or production
support.

## Planned first preview

The proposed first candidate is Android API 34+:

- `arm64-v8a`: runtime support requires final API 34 and API 35 acceptance from
  the Maven-resolved candidate.
- `x86_64`: compiled/alignment-only unless the final candidate is executed and
  separately accepted on that ABI.

The package will require Java 17 and its published metadata will enumerate all
transitive dependencies. Physical-device evidence is mandatory before a
production-use statement, but the public Developer Preview may remain explicitly
non-production while that gate is open.

## Unavailable until separately accepted

- Apple iOS 16 arm64 device/simulator and macOS 13 arm64
- Supported Chromium secure, cross-origin-isolated browser profile
- .NET 10 Linux ARM64 desktop
- Windows, Linux x64, macOS x64, other browsers, and other architectures

Unavailable targets have no placeholder packages or assets.
