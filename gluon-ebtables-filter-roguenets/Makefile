include $(TOPDIR)/rules.mk

PKG_NAME:=gluon-ebtables-filter-roguenets
PKG_VERSION:=1
PKG_RELEASE:=$(GLUON_VERSION).$(GLUON_SITE_CODE)-$(GLUON_RELEASE).$(GLUON_CONFIG_VERSION)

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/gluon-ebtables-filter-roguenets
  SECTION:=ffrl
  CATEGORY:=Gluon
  TITLE:=GLUON net-specific ebtables rules to filter unreasonable L2 traffic. Forked from Freifunk Paderborn
  DEPENDS:=+gluon-core +gluon-ebtables
  MAINTAINER:=Cyrus Fox <cyrus@lambdacore.de>
  URL:=https://github.com/ffrl/gluon-ebtables-filter-roguenets
  SOURCE:=git@github.com:ffrl/gluon-ebtables-filter-roguenets.git
endef

define Package/gluon-ebtables-filter-roguenets/description
	This package adds an additional layer-2 filter ruleset to filter out rogue IP addresses
	which are not part of the Freifunk Community network.
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/gluon-ebtables-filter-roguenets/install
	$(INSTALL_DIR) $(1)/lib/gluon/ebtables/
	$(CP) ./files/lib/gluon/ebtables/100-roguenets-net-chain $(1)/lib/gluon/ebtables/
	$(CP) ./files/lib/gluon/ebtables/110-roguenets-net-allow-ipv4-space $(1)/lib/gluon/ebtables/
	$(CP) ./files/lib/gluon/ebtables/110-roguenets-net-allow-ipv6-spaces $(1)/lib/gluon/ebtables/
	$(CP) ./files/lib/gluon/ebtables/400-add-roguenets-net-chain $(1)/lib/gluon/ebtables/
endef

$(eval $(call BuildPackage,gluon-ebtables-filter-roguenets))
