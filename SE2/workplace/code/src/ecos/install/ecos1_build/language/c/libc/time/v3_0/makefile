# eCos makefile

# This is a generated file - do not edit

export PREFIX := /home/ezequiel/Dropbox/disciplinas/se2/1112ver/ecos/install/ecos1_install
export COMMAND_PREFIX := arm-eabi-
export CC := $(COMMAND_PREFIX)gcc
export OBJCOPY := $(COMMAND_PREFIX)objcopy
export HOST := UNIX
export AR := $(COMMAND_PREFIX)ar

export REPOSITORY := /home/ezequiel/work/ecos/se2_ecos-3.0/packages
PACKAGE := language/c/libc/time/v3_0
OBJECT_PREFIX := language_c_libc_time
CFLAGS := -Wall -Wpointer-arith -Wstrict-prototypes -Wundef -Woverloaded-virtual -Wno-write-strings -mno-thumb-interwork -mcpu=arm7tdmi -g -O2 -ffunction-sections -fdata-sections -fno-rtti -fno-exceptions -Wno-format
LDFLAGS := -mno-thumb-interwork -mcpu=arm7tdmi -Wl,--gc-sections -Wl,-static -g -nostdlib
VPATH := $(REPOSITORY)/$(PACKAGE)
INCLUDE_PATH := $(INCLUDE_PATH) -I$(PREFIX)/include $(foreach dir,$(VPATH),-I$(dir) -I$(dir)/src -I$(dir)/tests) -I.
MLT := $(wildcard $(REPOSITORY)/$(PACKAGE)/include/pkgconf/mlt*.ldi $(REPOSITORY)/$(PACKAGE)/include/pkgconf/mlt*.h)
TESTS := tests/asctime tests/clock tests/ctime tests/gmtime tests/localtime tests/mktime tests/strftime tests/time tests/strptime

build: headers libtarget.a.stamp

LIBRARY := libtarget.a
COMPILE := src/asctime.cxx src/clock.cxx src/ctime.cxx src/difftime.cxx src/gmtime.cxx src/localtime.cxx src/mktime.cxx src/settime.cxx src/strftime.cxx src/time.cxx src/timeutil.cxx src/asctime_r.cxx src/ctime_r.cxx src/gmtime_r.cxx src/localtime_r.cxx src/strptime.cxx
OBJECTS := $(COMPILE:.cxx=.o.d)
OBJECTS := $(OBJECTS:.cpp=.o.d)
OBJECTS := $(OBJECTS:.c=.o.d)
OBJECTS := $(OBJECTS:.S=.o.d)

$(LIBRARY).stamp: $(OBJECTS)
	$(AR) rcs $(PREFIX)/lib/$(@:.stamp=) $(foreach obj,$?,$(if $(obj:%.o=),$(dir $(obj))$(OBJECT_PREFIX)_$(notdir $(obj:.o.d=.o)),$(obj)))
	@cat $(foreach obj,$^,$(obj:.o=.o.d)) > $(@:.stamp=.deps)
	@touch $@

headers: mlt_headers $(PREFIX)/include/cyg/libc/time/time.h $(PREFIX)/include/cyg/libc/time/timeutil.h $(PREFIX)/include/cyg/libc/time/time.inl

$(PREFIX)/include/cyg/libc/time/time.h: $(REPOSITORY)/$(PACKAGE)/include/time.h
	@mkdir -p $(dir $@)
	@cp $< $@
	@chmod u+w $@

$(PREFIX)/include/cyg/libc/time/timeutil.h: $(REPOSITORY)/$(PACKAGE)/include/timeutil.h
	@mkdir -p $(dir $@)
	@cp $< $@
	@chmod u+w $@

$(PREFIX)/include/cyg/libc/time/time.inl: $(REPOSITORY)/$(PACKAGE)/include/time.inl
	@mkdir -p $(dir $@)
	@cp $< $@
	@chmod u+w $@

include $(REPOSITORY)/pkgconf/rules.mak

