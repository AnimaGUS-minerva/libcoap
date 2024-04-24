PKG_NAME=libcoap
PKG_URL=https://github.com/AnimaGUS-minerva/libcoap
PKG_VERSION=93554c1769a90cc8ba2c06e9a3b71f22ddf1540d
PKG_LICENSE=BSD-2-Clause

LIBCOAP_BUILD_DIR=$(BINDIR)/pkg/$(PKG_NAME)
LIBCOAP_SOURCE_DIR=$(RIOTBASE)/build/pkg/$(PKG_NAME)
LIBCOAP_INCLUDE_DIR=$(RIOTBASE)/build/pkg/$(PKG_NAME)/include/coap3

include $(RIOTBASE)/pkg/pkg.mk

ifneq (,$(filter libcoap_oscore,$(USEMODULE)))
    all: libcoap libcoap_oscore
else
    all: libcoap
endif

libcoap:
	$(QQ)@cp $(LIBCOAP_SOURCE_DIR)/coap_config.h.riot $(LIBCOAP_SOURCE_DIR)/coap_config.h
	$(QQ)@cp $(LIBCOAP_INCLUDE_DIR)/coap.h.riot $(LIBCOAP_INCLUDE_DIR)/coap.h
	$(QQ)"$(MAKE)" -C $(LIBCOAP_SOURCE_DIR)/src -f $(CURDIR)/Makefile.libcoap

libcoap_oscore:
	$(QQ)"$(MAKE)" -C $(LIBCOAP_SOURCE_DIR)/src/oscore -f $(CURDIR)/Makefile.oscore
