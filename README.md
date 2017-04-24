*xkcptun is in the openwrt package feed now and maintenance will happen there*

OpenWrt-xkcptun
=================

A simple [OpenWrt](https://openwrt.org) package for the [xkcptun](https://github.com/liudf0716/xkcptun).

### Where to download packages?

Check the [release section](https://github.com/gigibox/openwrt-xkcptun/releases) for the most recent release!

### How to build a OpenWrt .ipk package?

These commands show how to build an OpenWrt a package(ipk) of xkcptun
<pre>
git clone -b chaos_calmer git://github.com/openwrt/openwrt.git

cd openwrt

echo "src-git xkcptun https://github.com/gigibox/openwrt-xkcptun.git" >> feeds.conf.default

./scripts/feeds update xkcptun
./scripts/feeds install xkcptun

make defconfig
make menuconfig
</pre>

You are now shown the OpenWrt configuration interface.
Select the appropiate "Target System" and "Target Profile".
This depends on what target chipset/router you want to build for.
Here is an example on what you might want to select:

<pre>
Target System (Atheros AR7xxx/AR9xxx)
Target Profile (TP-LINK TL-WR841N/ND)
Network  ---> < M > xkcptun
</pre>

Exit and save the settings. Then build the packages:

<pre>
make package/xkcptun/compile V=s
</pre>

The ipk packages can now be found in `bin/ar71xx/packages/xkcptun/`.
