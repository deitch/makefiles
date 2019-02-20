# Makefiles

Repo containing various useful Makefiles.

* `multiarch.mk` - Makefile to build golang binaries on multiple architectures, as well as docker images for each architecture and a multi-arch manifest

## Usage

### multiarch

* `build`: build for current architecture and OS
* `build-all`: build for all architectures and OSes
* `image`: make an OCI image tagged `latest` for the current architecture and OS
* `image-all`: make OCI images tagged `latest` for all architectures and OSes
* `test`: build and run tests

Include it in your Makefile and set the following parameters:
*  `BUILD_IMAGE` - the name of the OCI image as will be pushed to repo - required
*  `BUILDER_IMAGE` - the name of the image to use to build - optional, defaults to `golang:latest`
*  `PACKAGE_NAME` - the name of the package relatie to `$GOPATH/src/` - required


For example, download it as `multiarch.mk` and then in your main `Makefile`:

```make
BUILD_IMAGE=myorg/myrepo
PACKAGE_NAME=github.com/myorg/myrepo
include multiarch.mk
```
