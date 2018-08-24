# Author: Daniel Knox <d.knox@kent.ac.uk>

include $(TOPDIR)/rules.mk

PKG_NAME:=lora_packet_forwarder_legacy
PKG_VERSION:=4.0.1
PKG_RELEASE:=1
PKG_MAINTAINER:=Dan Knox <d.knox@kent.ac.uk>

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git://github.com/danielknox/packet_forwarder.git
PKG_SOURCE_VERSION:=legacy
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/lora_packet_forwarder_legacy
  TITLE:=Lora Packet Forwarder Legacy
	DEPENDS:=+lora_gateway
	SECTION:=net
  CATEGORY:=Network
  SUBMENU:=Lora
endef

define Package/lora_packet_forwarder_legacy/description
	LoRa Packet forwarder for Linux based gateways
endef

TARGET_CFLAGS += $(FPIC) -O2 -Wall -Wextra -std=c99 -Iinc -I.

define Package/lora_packet_forwarder_legacy/install
	$(INSTALL_DIR) $(1)/root/lora_pkt_fwd
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/poly_pkt_fwd/poly_pkt_fwd $(1)/root/lora_pkt_fwd
endef

$(eval $(call BuildPackage,lora_packet_forwarder_legacy))
