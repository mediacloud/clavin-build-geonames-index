Build [CLAVIN GeoNames.org index](https://github.com/Berico-Technologies/CLAVIN) on CI and release it on GitHub as a binary.

To make a new release:

```
git flow release start $(date +%F)
git flow release finish $(date +%F)
git push -u origin develop
git push -u origin master
git push --tags
```

...and wait for [![Build index, release package](https://github.com/mediacloud/clavin-build-geonames-index/workflows/Build%20index,%20release%20package/badge.svg)](https://github.com/mediacloud/clavin-build-geonames-index/actions) to complete. Upon completion, the prebuilt index will end up in [releases](https://github.com/mediacloud/clavin-build-geonames-index/releases).

Note that this repository pins the `CLAVIN` submodule at [this commit](https://github.com/Novetta/CLAVIN/tree/c38832ff63e3118427162faf30b87d9e4f2b201b) from 2016. The `logback.xml` file in the root directory here
patches that project during the build, via `.travis.yml`, to decrease its logging verbosity. If you want to pin `CLAVIN` to a more recent commit, make sure you review the project to see whether the directory structure has changed and, consequently, whether the `mv ./logback.xml` command in `.travis.yml` needs to be adjusted.
