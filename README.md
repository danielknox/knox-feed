# knox-feed
OpenWrt/LEDE feed containing packages (mostly LoRaWAN). There's a lot of SPI problems with the Linkit Smart, so this won't run without some kernel patching - https://github.com/narioinc/mt76xx-spi-half-duplex-patch/. I've still not been able to get the concentrators to sucessfully start from the packet forwarders (ERROR: [main] failed to start the concentrator), but I have managed to get the spi tests passed and the packet logger working.
