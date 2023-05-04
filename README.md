# x86_64

make -j$[$(nproc)+1]

make -j1 V=s

sed -i '$a src-git own_packages https://github.com/ThingsWhy/own_packages.git;main' feeds.conf.default

./scripts/feeds update -a
./scripts/feeds install -a

make menuconfig
