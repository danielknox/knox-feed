# Author: Daniel Knox <d.knox@kent.ac.uk>

include $(TOPDIR)/rules.mk

PKG_NAME:=lora_multi_protocol_packet_forwarder
PKG_VERSION:=3.0.10
PKG_RELEASE:=1
PKG_MAINTAINER:=Dan Knox <d.knox@kent.ac.uk>

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git://github.com/kersing/packet_forwarder.git
PKG_SOURCE_VERSION:=master
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/lora_multi_protocol_packet_forwarder
  TITLE:=Lora Multi Protocol Packet Forwarder
	DEPENDS:=+lora_gateway +ttn-gateway-connector
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=Lora
endef

define Package/lora_multi_protocol_packet_forwarder/description
 Multi protocol LoRa Packet forwarder for Linux based gateways
endef

TARGET_CFLAGS += $(FPIC) -O2 -Wall -Wextra -std=c99 -Iinc -I.

define Package/lora_multi_protocol_packet_forwarder/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mp_pkt_fwd/mp_pkt_fwd $(1)/usr/bin
	$(INSTALL_DIR) $(1)/etc/lora
	$(INSTALL_CONF) $(PKG_BUILD_DIR)/mp_pkt_fwd/global_conf.json $(1)/etc/lora/global_conf.sample.json
	$(INSTALL_CONF) $(PKG_BUILD_DIR)/mp_pkt_fwd/local_conf.json.sample $(1)/etc/lora/local_conf.sample.json
endef

$(eval $(call BuildPackage,lora_multi_protocol_packet_forwarder))
