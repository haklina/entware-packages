# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=mg
PKG_VERSION:=6.6
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/ibara/mg/tar.gz/$(PKG_NAME)-$(PKG_VERSION)?
PKG_HASH:=e8440353da1a52ec7d40fb88d4f145da49c320b5ba31daf895b0b0db5ccd0632
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_NAME)-$(PKG_VERSION)

PKG_MAINTAINER:=Hirokazu MORIKAWA <morikw2@gmail.com>
PKG_LICENSE:=PUBLICDOMAIN ISC BSD VARIOUS
PKG_LICENSE_FILES:=README.md

include $(INCLUDE_DIR)/package.mk

define Package/mg
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:=+libncurses +libpcre
  TITLE:=microscopic EMACS style editor
  URL:=https://github.com/ibara/mg
  SUBMENU:=Editors
endef

define Package/mg/description
 Mg is intended to be a small, fast, and portable editor for people who
 can't (or don't want to) run emacs for one reason or another, or are not
 familiar with the vi editor. It is compatible with emacs because there
 shouldn't be any reason to learn more editor types than emacs or vi.
endef

EXTRA_CFLAGS=$(TARGET_CPPFLAGS)

define Package/mg/install
	$(INSTALL_DIR) $(1)/opt/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mg $(1)/opt/bin/
endef

$(eval $(call BuildPackage,mg))
