# Author: Daniel Knox <d.knox@kent.ac.uk>

include $(TOPDIR)/rules.mk

PKG_NAME:=ttn-gateway-connector
PKG_VERSION:=v1.0.0
PKG_RELEASE:=v1.0.0
PKG_MAINTAINER:=Dan Knox <d.knox@kent.ac.uk>

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git://github.com/kersing/ttn-gateway-connector.git
PKG_SOURCE_VERSION:=master
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
# We override "packagename-packageversion", because
# other packages reference to the build dir of this package
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

PKG_FIXUP:=autoreconf

include $(INCLUDE_DIR)/package.mk

define Package/ttn-gateway-connector
  TITLE:=TTN Gateway Connector
  SECTION:=libs
  CATEGORY:=Libraries
  DEPENDS:= +libprotobuf-c +paho.mqtt.embedded-c +libpthread
endef

define Build/Configure
  $(CP) $(PKG_BUILD_DIR)/config.mk.in $(PKG_BUILD_DIR)/config.mk
endef

define Package/ttn-gateway-connector/description
  Runtime to establish mqtt connections to ttn backend
endef

define Package/ttn-gateway-connector/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/bin/libttn-gateway-connector.so $(1)/usr/lib/
endef

$(eval $(call BuildPackage,ttn-gateway-connector))
