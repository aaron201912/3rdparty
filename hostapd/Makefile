.PHONY: all
OUT_PATH := $(shell pwd)/out
3RD_PART_H += -I$(OUT_PATH)/../../openssl/include
3RD_PART_H += -I$(OUT_PATH)/../../libnl/include/libnl3
3RD_PART_LIB += -L$(OUT_PATH)/../../openssl/lib/dynamic
3RD_PART_LIB += -L$(OUT_PATH)/../../libnl/lib/dynamic

export 3RD_PART_H 3RD_PART_LIB

all:
	rm -rf $(OUT_PATH)
	mkdir -p $(OUT_PATH)
	tar -vxf hostapd-2.9.tar.gz -C $(OUT_PATH)
	cd $(OUT_PATH)/hostapd-2.9/hostapd;	\
	$(MAKE) CC=$(TOOLCHAIN_REL)gcc && $(MAKE) install BINDIR=$(shell pwd)/bin;	\
	cd -;
	mkdir -p $(shell pwd)/bin
	rm -rf $(OUT_PATH)
