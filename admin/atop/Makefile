#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=atop
PKG_RELEASE:=1
PKG_VERSION:=2.5.0
PKG_LICENSE:=GPL-2.0-or-later
PKG_SOURCE_URL:=https://www.atoptool.nl/download/
PKG_HASH:=4b911057ce50463b6e8b3016c5963d48535c0cddeebc6eda817e292b22f93f33

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_MAINTAINER:=Toni Uhlig <matzeton@googlemail.com>

include $(INCLUDE_DIR)/package.mk

define Package/atop
  SECTION:=admin
  CATEGORY:=Administration
  TITLE:=System and process monitor for Linux
  DEPENDS:=+zlib +libncurses
  URL:=https://www.atoptool.nl/
  MAINTAINER:=Toni Uhlig <matzeton@googlemail.com>
endef

define Package/atop/description
  Atop is an ASCII full-screen performance monitor for
  Linux that is capable of reporting the activity of all
  processes (even if processes have finished during the
  interval), daily logging of system and process activity
  for long-term analysis, highlighting overloaded system
  resources by using colors, etcetera. At regular
  intervals, it shows system-level activity related to the
  CPU, memory, swap, disks (including LVM) and network
  layers, and for every process (and thread) it shows e.g.
  the CPU utilization, memory growth, disk utilization,
  priority, username, state, and exit code. In combination
  with the optional kernel module netatop, it even shows
  network activity per process/thread.
endef

# Entware specific:
TARGET_CFLAGS += -DNOPERFEVENT

MAKE_FLAGS += \
	CFLAGS+="-Wno-misleading-indentation -Wno-unused-const-variable -Wno-format-truncation"

define Package/atop/install
	$(INSTALL_DIR) $(1)/opt/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/atop $(1)/opt/bin/
endef

$(eval $(call BuildPackage,atop))
