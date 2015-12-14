#
# Dockerfile for tesseract
#

FROM debian:jessie
MAINTAINER Anton Glukhov <anton.a.glukhov@gmail.com>

RUN apt-get update && apt-get install -y autoconf build-essential libtool git wget

# Leptonica 1.72
RUN wget http://leptonica.com/source/leptonica-1.72.tar.gz
RUN tar xvfz leptonica-1.72.tar.gz
RUN cd leptonica-1.72 && ./configure && make && make install

# Tesseract
RUN git clone https://github.com/tesseract-ocr/tesseract.git \
		&& cd tesseract \
		&& ./autogen.sh \
		&& ./configure \
		&& make \
		&& make install \

# Tessdata
RUN git clone https://github.com/tesseract-ocr/tessdata.git \
		&& cd tessdata \
		&& mv * /usr/local/share/tessdata/ \
		&& cd ..

ENTRYPOINT ["tesseract"]
CMD ["-h"]
