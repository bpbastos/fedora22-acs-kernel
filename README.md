# fedora22-acs-kernel
Fedora 22 (kernel 4.1.8) spec and acs-override patch

# Preparing

```bash

dnf install fedora-packager

rpmdev-setuptree

cd rpmbuild/SRPMS

dnf download --source kernel

rpm -i kernel*.src.rpm

cp kernel.spec rpmbuild/SPECS

cp override_for_missing_acs_capabilities.patch rpmbuild/SOURCE 

```

# Building

```bash

rpmbuild -ba rpmbuild/SPECS/kernel.spec --without=perf --without=tools --without=debug --without=debuginfo

```

