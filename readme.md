# Introduction

An Linux kernel level anti anti-debug solution. The patch hides TracerPid by setting it to zero in /proc/PID/status file.

# Build your own kernel

Prepare your CentOS 7 host

```
yum-builddep -y kernel
rpm -ivh https://buildlogs.centos.org/c7.1908.u.x86_64/kernel/20200205213736/3.10.0-1062.12.1.el7.x86_64/kernel-3.10.0-1062.12.1.el7.src.rpm
```

Apply the patch and build the RPM package

```
cp disable-tracerpid.patch ~/rpmbuild/SOURCES/linux-kernel-test.patch
rpm-build -bb ~/rpmbuild/SPECS/kernel.spec
```
