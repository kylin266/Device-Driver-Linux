PWD := $(shell pwd)

src-file = ./my_driver.c
obj-m += my_driver.o

CROSS := /home/dungnt98/gcc-linaro-7.4.1-2019.02-x86_64_arm-linux-gnueabihf/bin/arm-linux-gnueabihf-
KERNEL := /home/dungnt98/linux/

all:
	make ARCH=arm CROSS_COMPILE=$(CROSS) -C $(KERNEL) SUBDIRS=$(PWD) modules
clean:
	make -C $(KERNEL) SUBDIRS=$(PWD) clean
check:
	./checkpatch.pl --no-tree --ignore CONST_STRUCT --show-types -f $(src-file)

