.PHONY: all
OUT_PATH := $(shell pwd)/out

all:
	rm -rf $(OUT_PATH)
	mkdir -p $(OUT_PATH)
	tar -vxf jpegsrc.v9d.tar.gz -C $(OUT_PATH)
	cd $(OUT_PATH)/jpeg-9d;	\
	./configure --prefix=$(OUT_PATH)  CC=$(TOOLCHAIN_REL)gcc --enable-shared --enable-static --host=$(shell $(TOOLCHAIN_REL)gcc -dumpmachine);  \
	$(MAKE) && $(MAKE) install;	\
	cd -;
	mkdir -p $(shell pwd)/lib/$(TOOLCHAIN)/$(TOOLCHAIN_VERSION)/static/
	mv $(OUT_PATH)/lib/libjpeg.a $(shell pwd)/lib/$(TOOLCHAIN)/$(TOOLCHAIN_VERSION)/static/
	mkdir -p $(shell pwd)/lib/$(TOOLCHAIN)/$(TOOLCHAIN_VERSION)/dynamic/
	mv $(OUT_PATH)/lib/libjpeg.so $(shell pwd)/lib/$(TOOLCHAIN)/$(TOOLCHAIN_VERSION)/dynamic/
	mv $(OUT_PATH)/lib/libjpeg.so.9 $(shell pwd)/lib/$(TOOLCHAIN)/$(TOOLCHAIN_VERSION)/dynamic/
	mv $(OUT_PATH)/lib/libjpeg.so.9.4.0 $(shell pwd)/lib/$(TOOLCHAIN)/$(TOOLCHAIN_VERSION)/dynamic/
	cp $(OUT_PATH)/include $(shell pwd)/ -rf
	rm -rf $(OUT_PATH)
