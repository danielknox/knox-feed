# knox-feed
OpenWrt/LEDE feed containing packages (mostly LoRaWAN). There's a lot of SPI problems with the Linkit Smart 7688, so this won't run without some kernel patching - https://github.com/narioinc/mt76xx-spi-half-duplex-patch/. As such, I built my own openwrt based firmware from scratch and then uploaded it to my linkit. I needed this patch because any chunks greater than 16 bytes would cause a kernel panic (viewable by dmesg); as such the various lora gateway tests for spi were failing (https://docs.labs.mediatek.com/resource/linkit-smart-7688/en/limitations-and-known-issues). 

I'm also currently running the spi bus at 1MHz (within the lora gateway package) as I had concentrator start issues at 8MHz.
