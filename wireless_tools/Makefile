.PHONY: all
OUT_PATH := $(shell pwd)/out

all:
	rm -rf $(OUT_PATH)
	mkdir -p $(OUT_PATH)
	tar -vxf wireless_tools.29.tar.gz -C $(OUT_PATH)
	cd $(OUT_PATH)/wireless_tools.29;	\
	$(MAKE) CC=$(TOOLCHAIN_REL)gcc && $(MAKE) install PREFIX=$(shell pwd)/bin;	\
	cd -;
	mkdir -p $(shell pwd)/bin
	rm -rf $(OUT_PATH)
