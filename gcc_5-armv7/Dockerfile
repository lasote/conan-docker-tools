FROM lasote/conangcc5

LABEL maintainer="Luis Martinez de Bartolome <luism@jfrog.com>"

ENV CC=arm-linux-gnueabi-gcc-5 \
    CXX=arm-linux-gnueabi-g++-5 \
    CMAKE_C_COMPILER=arm-linux-gnueabi-gcc-5 \
    CMAKE_CXX_COMPILER=arm-linux-gnueabi-g++-5 \
    STRIP=arm-linux-gnueabi-strip \
    RANLIB=arm-linux-gnueabi-ranlib \
    AS=arm-linux-gnueabi-as \
    AR=arm-linux-gnueabi-ar \
    LD=arm-linux-gnueabi-ld \
    FC=arm-linux-gnueabi-gfortran-5

RUN sudo apt-get -qq update \
    && sudo apt-get -qq install -y --force-yes --no-install-recommends \
       ".*5.*arm-linux-gnueabi.*" \
    && sudo pip install -q --no-cache-dir conan --upgrade \
    && sudo rm -rf /var/lib/apt/lists/* \
    && conan profile new default --detect \
    && conan profile update settings.arch=armv7 default
