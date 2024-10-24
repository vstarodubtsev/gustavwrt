include $(TOPDIR)/rules.mk

PKG_NAME:=gustavd
PKG_VERSION:=1.0

PKG_RELEASE:=1
CMAKE_INSTALL:=1
PKG_FLAGS:=nonshared

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/vstarodubtsev/gustavd.git
PKG_SOURCE_VERSION:=$(PKG_VERSION)
PKG_MIRROR_HASH:=ed8cdb20f2361049ad8d43f8a96b6020328870edcf9cc898d0619df4c033fdde

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
