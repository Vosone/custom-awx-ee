# AWX EE

An Ansible Execution Environment for AWX project.

## Customizings

Additional code:
```
RUN update-ca-trust force-enable
ADD bundle-ca.crt /etc/pki/ca-trust/source/anchors/
RUN chmod 644 /etc/pki/ca-trust/source/anchors/*.crt && update-ca-trust extract
COPY krb5.conf /etc/krb5.conf
```

Custom files:
```
bundle-ca.crt > replace trough your cert from (own) custom ca
krb5.conf > replace it trough your kerberos config
```

## Regenerating the build context with podman:

```bash
$ tox -epodman
```

## Regenerating the build context with docker:

```bash
$ tox -edocker
```
