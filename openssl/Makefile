.PHONY: all
OUT_PATH := $(shell pwd)/out
unexport CROSS_COMPILE

all:
	rm -rf $(OUT_PATH)
	mkdir -p $(OUT_PATH)
	tar -vxf openssl-1.1.1g.tar.gz -C $(OUT_PATH)
	cd $(OUT_PATH)/openssl-1.1.1g;	\
	./Configure linux-armv4 --prefix=$(OUT_PATH) CC=$(TOOLCHAIN_REL)gcc;	\
	$(MAKE) && $(MAKE) install;	\
	cd -;
	mkdir -p $(shell pwd)/lib/$(TOOLCHAIN)/$(TOOLCHAIN_VERSION)/static
	cp $(OUT_PATH)/lib/*.a $(shell pwd)/lib/$(TOOLCHAIN)/$(TOOLCHAIN_VERSION)/static/ -rf
	mkdir -p $(shell pwd)/lib/$(TOOLCHAIN)/$(TOOLCHAIN_VERSION)/dynamic
	cp -d -rf $(OUT_PATH)/lib/* $(shell pwd)/lib/$(TOOLCHAIN)/$(TOOLCHAIN_VERSION)/dynamic/
	mkdir -p $(shell pwd)/include
	cp -rf $(OUT_PATH)/include $(shell pwd)/
	rm -rf $(OUT_PATH)
