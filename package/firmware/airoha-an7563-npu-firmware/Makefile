include $(TOPDIR)/rules.mk

PKG_NAME:=airoha-an7563-npu-firmware
PKG_VERSION:=1.0.0
PKG_RELEASE:=1

PKG_LICENSE:=Proprietary
PKG_LICENSE_FILES:=

include $(INCLUDE_DIR)/package.mk

define Package/airoha-an7563-npu-firmware
  SECTION:=firmware
  CATEGORY:=Firmware
  TITLE:=Airoha AN7563 NPU firmware (from EcoNet GPL drop)
  DEPENDS:=@TARGET_airoha_an7563
  DEFAULT:=y if TARGET_airoha_an7563
endef

define Package/airoha-an7563-npu-firmware/description
  NPU (Network Processor Unit) firmware blobs for Airoha AN7563 SoC.
  Extracted verbatim from the EcoNet GPL drop
  EXS27_EXS25_EXS18_GPL_V1.0.1.34_src kmod-npu/userfs/, renamed to
  the upstream-style airoha/an7563_npu_{rv32,data}.bin layout.
endef

define Build/Compile
endef

define Package/airoha-an7563-npu-firmware/install
	$(INSTALL_DIR) $(1)/lib/firmware/airoha
	$(INSTALL_DATA) ./src/an7563_npu_rv32.bin \
		$(1)/lib/firmware/airoha/an7563_npu_rv32.bin
	$(INSTALL_DATA) ./src/an7563_npu_data.bin \
		$(1)/lib/firmware/airoha/an7563_npu_data.bin
endef

$(eval $(call BuildPackage,airoha-an7563-npu-firmware))
