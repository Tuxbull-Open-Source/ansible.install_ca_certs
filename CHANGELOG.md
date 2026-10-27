# Changelog

## v1.0.0 - 2026-10-27

### Changed

- Migrate Galaxy identity to `tuxbull.install_ca_certs`.
- Modernize package, file, download, and CA-store refresh tasks.
- Align dispatch with the current role template and update documentation.

### Verified

- Disposable Rocky Linux 10 CA anchor installation, trust-store refresh, and
  same-input idempotency validation.
