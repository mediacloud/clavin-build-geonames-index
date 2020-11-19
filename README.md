Build [CLAVIN GeoNames.org index](https://github.com/Berico-Technologies/CLAVIN) on Travis and release it on GitHub as a binary.

To make a new release:

```
git flow release start $(date +%F)
git flow release finish $(date +%F)
git push -u origin develop
git push -u origin master
git push --tags
```

...and wait for [![Build Status](https://travis-ci.org/mediacloud/clavin-build-geonames-index.svg?branch=develop)](https://travis-ci.org/mediacloud/clavin-build-geonames-index) to complete. Upon completion, the prebuilt index will end up in [releases](https://github.com/mediacloud/clavin-build-geonames-index/releases).
