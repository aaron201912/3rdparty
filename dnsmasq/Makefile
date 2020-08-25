.PHONY: all
OUT_PATH := $(shell pwd)/out

all:
	rm -rf $(OUT_PATH)
	mkdir -p $(OUT_PATH)
	tar -vxf dnsmasq-2.82.tar.gz -C $(OUT_PATH)
	cd $(OUT_PATH)/dnsmasq-2.82;	\
	$(MAKE) install CC=$(TOOLCHAIN_REL)gcc PREFIX=$(OUT_PATH)/;	\
	cd -;
	mkdir -p $(shell pwd)/bin/$(TOOLCHAIN_VERSION)
	cp -rf $(OUT_PATH)/sbin/dnsmasq $(shell pwd)/bin/$(TOOLCHAIN_VERSION)
	rm -rf $(OUT_PATH)
