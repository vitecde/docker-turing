#FROM alpine:3.4
#FROM gliderlabs/alpine:3.4
FROM frolvlad/alpine-glibc

WORKDIR /tmp/ffmpeg

RUN apk add --update build-base 
RUN apk add git cmake 
RUN apk add boost boost-program_options boost-dev 
RUN apk add coreutils nasm  
RUN mkdir -p /usr/src 
RUN git clone https://github.com/bbc/turingcodec.git /usr/src/turing 
RUN cd /usr/src/turing && git checkout develop
RUN mkdir /usr/src/turing/build \
&& cd  /usr/src/turing/build \
&& cmake -DCMAKE_INSTALL_PREFIX="/usr" -DCMAKE_BUILD_TYPE=Debug ../   \
&& make \
&& make install 
RUN git clone https://github.com/kupix/FFmpeg-1.git -b libturing /usr/src/ffmpeg 
RUN cd /usr/src/ffmpeg \
&& ./configure --prefix=/usr/ --enable-libturing --enable-gpl --enable-static --disable-shared --enable-debug --disable-stripping \
&&  make \
&& make install 
#\
#&& rm -rf /usr/src \
#&& apk del boost-dev cmake git coreutils yasm build-base 

#ENTRYPOINT ["ffmpeg"]
