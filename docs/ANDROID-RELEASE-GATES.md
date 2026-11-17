# Android `0.6.0-preview.1` technical release gates

This inventory tracks the remaining engineering work for a new public Android
Developer Preview. It is not publication authorization and cannot be satisfied
by renaming an internal artifact.

## 1. Clean and legally usable inputs

- Reconcile the current dirty/private implementation checkout without
  overwriting another contributor's work.
- Freeze one clean reviewed `main` commit and exact build-input manifest.
- Add the counsel/owner-approved public binary SDK license; retain the separate
  proprietary source license internally.
- Complete third-party redistribution review, notices, and SPDX/CycloneDX SBOM.
- Freeze approved public README, API reference, changelog, security/support
  policies, mandatory warning, and package metadata.

## 2. Public Android namespace migration

The owner approved `com.conchprotocol.sdk`. The current private implementation
uses `app.sanksh.conch`; the new public candidate therefore requires one reviewed
API/foreign-boundary migration, not a metadata-only rename:

- Kotlin and Java package declarations and source paths;
- Android Gradle namespace and instrumentation runner;
- consumer imports and isolated consumer application namespace;
- R8/ProGuard keep rules and callback interface names;
- host checks, instrumentation identifiers, and local acceptance runner;
- every exported JNI symbol currently named
  `Java_app_sanksh_conch_NativeBridge_*`, changed consistently to
  `Java_com_conchprotocol_sdk_NativeBridge_*`;
- API signature dump, documentation names, examples, tests, and package scans.

No compatibility alias is assumed. Because only internal packages exist, the
specification and coordinator must explicitly accept this public API break before
the public freeze. Protocol, wire, storage, command, and C ABI bytes must remain
unchanged.

## 3. New release artifact

- Build a new release AAR named for `0.6.0-preview.1` from the accepted clean
  revision using pinned JDK 17, Android SDK/Build Tools 36, NDK, Gradle, AGP, and
  dependency locks.
- Ensure the package contains only compiled public JVM classes, manifest,
  consumer rules, backup/transfer exclusions, and complete `arm64-v8a` and
  `x86_64` native pairs—no implementation source, fixtures, tests, debug data,
  source maps, private endpoints, credentials, or internal provenance.
- Bind the artifact to source/build inputs and record whether binary
  reproducibility was actually established.
- Inspect ELF architecture and 16 KiB load alignment for every native library.

## 4. Maven candidate

- Stage the approved coordinate
  `com.conchprotocol:conch-android:0.6.0-preview.1` locally.
- Produce AAR, POM, Gradle Module Metadata, public API documentation artifact,
  approved SDK license, notices, SBOM, README, changelog, support/security links,
  checksums, and company signatures.
- Publish exact Kotlin/runtime requirements and no unavailable platform assets.
- Validate archive paths, collisions, symlinks, expanded size, secret/private
  content, dependency metadata, signatures, and final Maven-resolved hashes.

## 5. Final-package consumers and runtime

- Build fresh debug and release/minified applications from only the staged Maven
  repository with no implementation checkout reference.
- Inspect merged manifest, backup rules, R8 output, APK/AAB native assets, and
  dependency graph.
- On API 34 and API 35 ARM64, execute public custody create/open/reopen,
  metadata, two-party exchange, exact receive rejection, receipt/ACK recovery,
  interrupted enrollment, process-kill cuts, and negative missing/corrupt/
  restored/rollback cases.
- Test authenticated external-anchor mode against an isolated gateway and local
  durability separately; never merge their claims.
- Keep x86_64 labeled compiled/alignment-only unless the final Maven candidate is
  executed there.
- Complete physical-device lock/restart/upgrade/backup-exclusion testing before
  any production claim.

## 6. Final approval

- Specification role reviews the exact frozen bytes and issues a bounded verdict.
- Govind Prajapati, Project Lead, reviews the exact package and evidence as the
  named human release approver.
- Company signing/checksum records are created through protected release keys.
- Manual Maven Central publication occurs only after the owner gives a separate
  explicit approval for the exact bytes and destination.
