obj-m := aiy-adc.o
ccflags-y := -std=gnu99 -Wno-declaration-after-statement -I$(src)/../../include
KVERSION := $(shell uname -r)
all:
	$(MAKE) -C /lib/modules/$(KVERSION)/build M=$(PWD) modules
clean:
	$(MAKE) -C /lib/modules/$(KVERSION)/build M=$(PWD) clean
