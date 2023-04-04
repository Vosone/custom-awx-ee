# Custom Ansible AWX EE

An Ansible Execution Environment for AWX project.

## Customizings

Additional code in Containerfile:
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

Define your url in tox.ini

For working correct, add this line in awx templates:
```
ansible_winrm_ca_trust_path: /etc/pki/ca-trust/source/anchors/bundle-ca.crt
```

## Regenerating the build context with podman:

```bash
$ tox -epodman
```

## Regenerating the build context with docker:

```bash
$ tox -edocker
```
