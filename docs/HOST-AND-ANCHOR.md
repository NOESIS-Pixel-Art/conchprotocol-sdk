# Host and rollback-anchor requirements

A remote ConchProtocol owner requires an authenticated, durable, linearizable
compare-and-swap anchor outside the client snapshot rollback domain. A local
file, application database row, IndexedDB record, key-value preference, or
counter stored beside the encrypted snapshots is not an independent anchor.

The anchor must preserve one monotonic head per exact store, authenticate every
request, refuse reset/delete/decrease behavior, return ambiguous network outcomes
as unknown, and remain consistent across backup, restore, failover, upgrade, and
operator recovery. Capabilities and credentials must not enter logs.

No hosted ConchProtocol anchor is publicly available yet. A self-hosted gateway
or company-hosted service will be documented only after its exact topology,
authentication, provisioning, TLS, backup/restore, monitoring, revocation,
incident, privacy, and operator-trust boundaries pass review.

The application must separately implement protected durable intent/receipt
coupling. The anchor does not make application database effects exactly once,
authenticate peer identities, provide transport delivery, or recover missing
custody. Unknown outcomes require exact recovery; they never authorize a fresh
identity, fresh ticket, state deletion, or anchor reset.
