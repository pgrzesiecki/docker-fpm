# Description

Unofficial Docker container for [fpm package management](https://fpm.readthedocs.io/en/latest/) with which you can create new and modify existing packages.

**Sources:**
* gem (even autodownloaded for you)
* python modules (autodownload for you)
* pear (also downloads for you)
* directories
* tar(.gz) archives
* rpm
* deb
* node packages (npm)
* pacman (ArchLinux) packages

**Targets:**
* deb
* rpm
* solaris
* freebsd
* tar
* directories
* Mac OS X .pkg files (osxpkg)
* pacman (ArchLinux) packages

Please visit [official fpm wiki](https://github.com/jordansissel/fpm/wiki) to read more and check all available params.

## Usage

```bash
# simple
docker run --rm -v $(pwd):/build pgrzesiecki/docker-fpm -s dir -t rpm -n my-rpm-package -v v1.0 ./

#more advanced
docker run --rm -v $(pwd):/build pgrzesiecki/docker-fpm -s dir -t rpm -n my-rpm-package -v v1.0 --after-install scripts/run-after-install.sh -d g++ dir1 dir2 file.log other-filze.sh
```

Remember to mount `/build` volume with files to pack.

