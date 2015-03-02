include $(TOPDIR)/rules.mk

PKG_NAME:=ffpb-ebtables-net-rules
PKG_VERSION:=1
PKG_RELEASE:=$(GLUON_VERSION).$(GLUON_SITE_CODE)-$(GLUON_RELEASE).$(GLUON_CONFIG_VERSION)

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/ffpb-ebtables-net-rules
  SECTION:=ffpb
  CATEGORY:=Gluon
  TITLE:=FFPB net-specific ebtables rules to filter unreasonable L2 traffic.
  DEPENDS:=+gluon-core +gluon-ebtables
  MAINTAINER:=Freifunk Paderborn <maschinenraum@paderborn.freifunk.net>
  URL:=https://git.c3pb.de/freifunk-pb/ffpb-packages
  SOURCE:=git@git.c3pb.de:freifunk-pb/ffpb-packages.git
endef

define Package/ffpb-ebtables-net-rules/description
	This package adds an additional layer-2 filter-ruleset to prevent traffic,
	which is not destined for any Freifunk Paderborn layer-3 specific target,
	from entering the network via the nodes.
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/ffpb-ebtables-net-rules/install
	$(INSTALL_DIR) $(1)/lib/gluon/ebtables/
	$(CP) ./files/lib/gluon/ebtables/100-ffpb-net-chain $(1)/lib/gluon/ebtables/
	$(CP) ./files/lib/gluon/ebtables/110-ffpb-net-allow-ipv4-space $(1)/lib/gluon/ebtables/
	$(CP) ./files/lib/gluon/ebtables/110-ffpb-net-allow-ipv6-spaces $(1)/lib/gluon/ebtables/
	$(CP) ./files/lib/gluon/ebtables/400-add-ffpb-net-chain $(1)/lib/gluon/ebtables/
endef

$(eval $(call BuildPackage,ffpb-ebtables-net-rules))
