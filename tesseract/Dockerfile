
# Dockerfile for tesseract
#

FROM debian:jessie
MAINTAINER Anton Glukhov <anton.a.glukhov@gmail.com>

RUN apt-get update && apt-get install -y autoconf build-essential libtool git wget

# Leptonica 1.72
RUN wget http://leptonica.com/source/leptonica-1.72.tar.gz \
		&& tar xvfz leptonica-1.72.tar.gz \
		&& cd leptonica-1.72 \
		&& ./configure \
		&& make \
		&& make install \
		&& cd ..

# Tesseract
RUN git clone https://github.com/tesseract-ocr/tesseract.git \
		&& cd tesseract \
		&& ./autogen.sh \
		&& ./configure \
		&& make \
		&& make install \
		&& cd ..

ENV PATH /usr/local/bin:$PATH
ENV LD_LIBRARY_PATH /usr/local/lib
