all: modules

modules:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) modules $(KBUILD_OPTIONS)

modules_install:
	$(MAKE) INSTALL_MOD_STRIP=1 -C $(KERNEL_SRC) M=$(M) modules_install

%:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) $@ $(KBUILD_OPTIONS)

clean:
	rm -f *.o *.ko *.mod.c *.mod.o *~ .*.cmd Module.symvers
	rm -rf .tmp_versions

KBUILD_EXTRA_SYMBOLS += $(M)/../../../mmi_info/$(GKI_OBJ_MODULE_DIR)/Module.symvers
KBUILD_EXTRA_SYMBOLS += $(M)/../touchscreen_mmi/$(GKI_OBJ_MODULE_DIR)/Module.symvers
ifneq ($(filter m y, $(CONFIG_INPUT_GTP_PASSIVE_PEN_NOTIFIER)),)
KBUILD_EXTRA_SYMBOLS += $(M)/../../../misc/hall/$(GKI_OBJ_MODULE_DIR)/Module.symvers
endif
