Tesseract
=========

![](https://badge.imagelayers.io/toxxin/tesseract:latest.svg)

Tesseract is an open source OCR engine available under the Apache 2.0 license.


## How to use:
```
$ docker run --rm toxxin/tesseract tesseract --help
$ docker run --rm -v `pwd`:/work toxxin/tesseract tesseract image.jpg out
$ less out.txt
```
