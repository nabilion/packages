#
# Copyright (C) 2007-2019 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-requests
PKG_VERSION:=2.21.0
PKG_RELEASE:=2
PKG_LICENSE:=Apache-2.0

PKG_SOURCE:=requests-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/r/requests
PKG_HASH:=502a824f31acdacb3a35b6690b5fbf0bc41d63a24a45c4004352b0242707598e
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-requests-$(PKG_VERSION)

PKG_CPE_ID:=cpe:/a:python-requests:requests

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-requests/Defaults
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  PKG_MAINTAINER:=Josef Schlehofer <josef.schlehofer@nic.cz>, Alexandru Ardelean <ardeleanalex@gmail.com>
  URL:=http://python-requests.org/
endef

define Package/python-requests
$(call Package/python-requests/Default)
  TITLE:=HTTP library for Python
  DEPENDS:= \
	  +PACKAGE_python-requests:python \
	  +PACKAGE_python-requests:python-chardet \
	  +PACKAGE_python-requests:python-idna \
	  +PACKAGE_python-requests:python-urllib3 \
	  +PACKAGE_python-requests:python-certifi
  VARIANT:=python
endef

define Package/python3-requests
$(call Package/python-requests/Default)
  TITLE:=HTTP library for Python3
  DEPENDS:= \
	  +PACKAGE_python3-requests:python3-light  \
	  +PACKAGE_python3-requests:python3-chardet  \
	  +PACKAGE_python3-requests:python3-idna  \
	  +PACKAGE_python3-requests:python3-urllib3  \
	  +PACKAGE_python3-requests:python3-certifi
  VARIANT:=python3
endef

define Package/python-requests/description
  Requests is the only Non-GMO HTTP library for Python, safe for human consumption.
endef

define Package/python3-requests/description
$(call Package/python-requests/description)
.
(Variant for Python3)
endef

$(eval $(call PyPackage,python-requests))
$(eval $(call BuildPackage,python-requests))
$(eval $(call BuildPackage,python-requests-src))

$(eval $(call Py3Package,python3-requests))
$(eval $(call BuildPackage,python3-requests))
$(eval $(call BuildPackage,python3-requests-src))
