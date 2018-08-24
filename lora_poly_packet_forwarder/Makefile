# Author: Daniel Knox <d.knox@kent.ac.uk>

include $(TOPDIR)/rules.mk

PKG_NAME:=lora_poly_packet_forwarder
PKG_VERSION:=4.0.1
PKG_RELEASE:=1
PKG_MAINTAINER:=Dan Knox <d.knox@kent.ac.uk>

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git://github.com/danielknox/lora_packet_forwarder_legacy.git
PKG_SOURCE_VERSION:=master
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/lora_poly_packet_forwarder
  TITLE:=Lora Poly Packet Forwarder
	DEPENDS:=+lora_gateway
	SECTION:=net
  CATEGORY:=Network
  SUBMENU:=Lora
endef

define Package/lora_poly_packet_forwarder/description
	LoRa Poly Packet forwarder for Linux based gateways
endef

TARGET_CFLAGS += $(FPIC) -O2 -Wall -Wextra -std=c99 -Iinc -I.

define Package/lora_poly_packet_forwarder/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/lora_pkt_fwd/lora_pkt_fwd $(1)/usr/bin
	endef

$(eval $(call BuildPackage,lora_poly_packet_forwarder))
