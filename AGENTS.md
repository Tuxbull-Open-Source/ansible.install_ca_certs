# Repository instructions

This repository provides the reusable `tuxbull.install_ca_certs` role. Keep it
focused on operating-system CA trust anchors. Do not commit private CA material,
credentials, inventories, generated trust stores, or lab artifacts. The bundled
demo certificate is for role testing only.

Validate YAML, Ansible syntax, a fresh disposable Linux-lab convergence, a
certificate-subject check in the platform trust store, and a no-change second
run. Test remote URL inputs only with a user-approved fixture and checksum;
never use an uncontrolled third-party certificate URL in tests.

`README.md` is usage documentation and `CHANGELOG.md` is release history. Source
repository is `Tuxbull-Open-Source/ansible.install_ca_certs`; Galaxy FQN is
`tuxbull.install_ca_certs`. Do not self-merge. After review and merge, create an
immutable SemVer tag and published GitHub Release, then import and verify both
unpinned and version-pinned Galaxy installations.
