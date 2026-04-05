obj-m := aiy-io-i2c.o
ccflags-y := -std=gnu99 -Wno-declaration-after-statement -I$(src)/../include
KVERSION := $(shell uname -r)
all:
	$(MAKE) -C /lib/modules/$(KVERSION)/build M=$(PWD) modules
clean:
	$(MAKE) -C /lib/modules/$(KVERSION)/build M=$(PWD) clean
