include $(TOPDIR)/rules.mk

PKG_NAME:=gustavd
PKG_RELEASE:=1
CMAKE_INSTALL:=1
PKG_FLAGS:=nonshared

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/vstarodubtsev/gustavd.git
PKG_SOURCE_DATE:=2024-10-24
PKG_SOURCE_VERSION:=b246a46fc41ac20d1ffc6c9a1074c1b6ad715e7d

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/gustavd
  SECTION:=base
  CATEGORY:=Base system
  TITLE:=Gustav AT daemon
  DEPENDS:=+kmod-usb-gadget-eth +kmod-usb-gadget-serial +kmod-usb-chipidea2
endef

define Package/gustavd/description
 descr
endef

define Package/gustavd/install
	$(INSTALL_DIR) $(1)/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/gustavd $(1)/sbin/

	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/usbgadget.init $(1)/etc/init.d/usbgadget
endef

$(eval $(call BuildPackage,gustavd))
