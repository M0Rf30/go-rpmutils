# RPM v6 test packages

Built with rpm 6.0.1 from `hello.spec` (a noarch package with a directory,
a regular file `a.txt` containing `hi\n`, and a symlink `b -> a.txt`):

    rpmbuild --define "_topdir $T" --define '_rpmformat 6' -bb hello.spec

- `ref-v6.rpm`: unsigned.
- `ref-v6s.rpm`: the same package signed with `rpmsign --addsign` using a
  throwaway key (`YAP Test`, key ID `0155CEF4D09A756C`). rpm 6 stores the
  signature as a base64 OpenPGP packet in signature tag 278 (OPENPGP).
- `yaptest.pub`: ASCII-armored public key of the signing key.
