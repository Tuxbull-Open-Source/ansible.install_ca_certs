# Install CA certificates role

Install PEM CA certificates into the operating-system trust store and refresh
that trust store.

## Variables

`ca_certificates` is a list of controller-local certificate paths, HTTP(S) URLs,
or mappings with `src` and optional `dest_name`.

```yaml
ca_certificates:
  - ca_demo.crt
  - src: https://example.invalid/ca.pem
    dest_name: example-ca.crt
```

Certificates from the controller are copied from the role's `files/` directory
or the playbook's search path. URL inputs are downloaded by the managed host.
Use a protected internal source for private CA material. Use `.crt` destination
names for Debian/Ubuntu because `update-ca-certificates` processes that suffix.

## Example

```yaml
- hosts: linux
  become: true
  roles:
    - role: tuxbull.install_ca_certs
      vars:
        ca_certificates:
          - ca_demo.crt
```

## Verification

The role refreshes the platform CA store when its managed anchors change. It
does not validate certificate ownership, expiry, revocation, or remote HTTPS
service behavior; verify those separately.
