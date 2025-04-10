# FinchDeb

This package contains the build script needed to build a FInch deb archive for Ubuntu and Debian.

Currently, this deb vends on top level package (`runfinch-finch`), which bundles a few other projects (`finch-buildkit`, `finch-soci`, `finch-daemon`, `containerd`, `runc`, `nerdctl`). These are bundled either because they don't provide packages on Ubuntu or because they are not yet considered stable. In the future, if they are spun out into their own packages, `package.sh` will be updated.

## Building

This directory contains a `package.sh` script which takes a few options as input. Running `./package.sh` will build the latest release specified in the `package.sh` file.

1. `./package.sh`
    1. Sets up temporary directories, to pull, build and install packages to the appropriate location, and builds Finch debs for `aarch64` and `x86_64`. By default, this requires internet access to download the sources.
1. Install the newly built deb (replace the version numbers and architecture as needed):

    ```shell
    sudo apt install ./finch_171_aarch64.deb -y
    ```

NOTE: To test changes, you will also first need to uninstall any existing version of the package using `sudo apt remove finch -y`.
