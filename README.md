*xkcptun is in the openwrt package feed now and maintenance will happen there*

OpenWrt-xkcptun
=================

This is an [OpenWrt](https://openwrt.org) package feed for [xkcptun](https://github.com/liudf0716/xkcptun).

### Where to download packages?

Check the [release section](https://github.com/gigibox/openwrt-xkcptun/releases) for the most recent release!

### How to build a OpenWrt .ipk package?

These commands show how to build an OpenWrt a package(ipk) of xkcptun
<pre>
cd openwrt

echo "src-git xkcptun https://github.com/gigibox/openwrt-xkcptun.git" >> feeds.conf.default

./scripts/feeds update xkcptun
./scripts/feeds install -a -p xkcptun
</pre>

The xkcptun packages should now appear in menuconfig.

<pre>
make menuconfig

Network  ---> < M > xkcptun

LuCI  ---> 3. Applications  ---> <*> luci-app-xkcptun
</pre>

Exit and save the settings. Then build the packages:

<pre>
make package/xkcptun/compile V=s
make package/luci-app-xkcptun/compile V=s
</pre>

The ipk packages can now be found in `bin/.../packages/xkcptun/`
