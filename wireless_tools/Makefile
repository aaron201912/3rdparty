.PHONY: all
OUT_PATH := $(shell pwd)/out

all:
	rm -rf $(OUT_PATH)
	mkdir -p $(OUT_PATH)
	tar -vxf wireless_tools.29.tar.gz -C $(OUT_PATH)
	cd $(OUT_PATH)/wireless_tools.29;	\
	$(MAKE) CC=$(TOOLCHAIN_REL)gcc && $(MAKE) install PREFIX=$(OUT_PATH);	\
	cd -;
	mkdir -p $(shell pwd)/include
	mkdir -p $(shell pwd)/lib/$(TOOLCHAIN_VERSION)
	mkdir -p $(shell pwd)/bin/$(TOOLCHAIN_VERSION)
	cp -rf $(OUT_PATH)/sbin/* $(shell pwd)/bin/$(TOOLCHAIN_VERSION)
	cp -rf -d $(OUT_PATH)/lib/* $(shell pwd)/lib/$(TOOLCHAIN_VERSION)
	cp -rf $(OUT_PATH)/include $(shell pwd)/
	rm -rf $(OUT_PATH)
