# Android integration boundary

> **ConchProtocol Developer Preview is experimental cryptographic software. It has not completed an independent security audit and must not protect production communications.**

No Android package is published yet, so this page intentionally contains no
dependency declaration or download instruction.

The approved public API namespace is `com.conchprotocol.sdk`. The planned Maven
identity is `com.conchprotocol:conch-android:0.6.0-preview.1`; it remains
unavailable until the exact candidate passes final review and manual publication
approval.

## Application obligations

An integrating application must:

- bind each owner to the exact account and installation identity;
- authenticate peer identities through a trusted external channel and preserve
  identity continuity;
- supply a protected durable application store whose commit atomically records
  the exact receipt and intended application effect;
- retry only immutable previously committed ciphertext;
- recover ambiguous outcomes before accepting new work;
- preserve custody, encrypted snapshots, backup exclusions, and owner
  serialization exactly as documented;
- use either the explicitly selected local-durability profile or an authenticated
  independent remote anchor without silent fallback between them;
- fail closed when custody, protected state, or anchor state is missing,
  conflicting, restored, or corrupt.

The SDK does not provide account management, message transport, identity
verification UI, content moderation, or a production rollback-anchor service.

## Local and remote modes

Remote mode requires the independent anchor described in
[HOST-AND-ANCHOR.md](HOST-AND-ANCHOR.md). Android local durability is a distinct,
explicit profile and is not independent anti-rollback protection. A mutually
consistent rollback of all local state remains possible. Local mode must never
be presented as equivalent to an independently operated remote anchor.
