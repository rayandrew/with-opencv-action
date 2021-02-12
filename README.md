# with-opencv-action

Cacheable OpenCV installation on your Github Actions

---

This repo is combination from several repo:
- [Install OpenCV Action](https://github.com/florianblume/install-opencv-action)
- [Setup OpenCV Action](https://github.com/Dovyski/setup-opencv-action)

All credits should belong to @florianblume and @Dovyski

## Options

See `action.yml`

~~~~
- name: Cache OpenCV
  id: copencv-cache
  uses: actions/cache@v2
  with:
    path: ./opencv-install
    key: ${{ runner.os }}-opencv-cache

- name: Install OpenCV
  uses: rayandrews/with-opencv-action@v1
  with:  
    dir: ./opencv-install
    cached: ${{ steps.opencv-cache.outputs.cache-hit }}
~~~~
