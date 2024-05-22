# Toradex oe-core Setup

To simplify installation we provide a manifest for the repo tool which manages
the different git repositories and the used versions.
[more on repo](https://code.google.com/p/git-repo/)

This manifest allows setting up TorizonCore or Toradex Images for ATDM platform.

Final build will prepare Tezi image that can be installed on ATDM board.

## Pre-requisite for yocto compilation

- [Guide for one time installation for specific platform](https://docs.yoctoproject.org/ref-manual/system-requirements.html#required-packages-for-the-build-host)

## Repo init link

Currently we are supporting kirkstone branch. We have also added support for master branch but not sure for compilation success.

repo init -u https://github.com/DeviceSolutions/toradex-manifest.git -b kirkstone-6.x.y -m torizoncore/default-atdm.xml
repo sync

## Prepare compilation environment

command: [MACHINE=<MACHINE>] source setup-environment [BUILDDIR]

example:
export LC_ALL="en_US.UTF-8"
export LC_CTYPE="en_US.UTF-8"
MACHINE=verdin-imx8mp source setup-environment build-verdin-imx8mp

## start compilation

bitbake torizon-core-docker

## Tezi image directory

[BUILDDIR]/deploy/images/verdin-imx8mp/

