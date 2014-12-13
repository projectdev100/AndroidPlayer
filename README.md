Android AV Player using ffmpeg and SDL2
====

depends
====
ffmpeg-11
SDL2

general instructions
====
for convience, put this line in your .bashrc:
export PATH=$PATH:/mnt/android-ndk-r10d:/mnt/android-sdk-linux/tools:/mnt/android-sdk-linux/platform-tools

do symbol links at first time:
./bootstrap.sh

compile native code:
ndk-build -j8 2>&1 | tee build.log

prepare project at first time:
android update project --path . --target android-21

generate apk:
ant debug

install to phone:
ant debug install