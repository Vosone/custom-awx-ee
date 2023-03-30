# AWX EE

An Ansible Execution Environment for AWX project.

## Customizings

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
