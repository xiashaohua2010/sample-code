
KDIR=/local/mnt/workspace/qemu/linux-4.14.217  #linux代码路径，没有详细研究依赖了那些文件，全部包含了
PWD=$(shell pwd)

# Kernel modules
obj-m += mmap4.o
module-objs = mmap4.o

ARCH=arm
CROSS_COMPILE=arm-linux-gnueabi-

CC := $(CROSS_COMPILE)gcc
LD := $(CROSS_COMPILE)ld

#EXTRA_CFLAGS=-g -O0

default:
	make -C $(KDIR) M=$(PWD) modules
clean:
	rm -f *.ko *.o *.mod.c *.symvers *.order


#:/local/mnt/workspace/qemu/linux-4.14.217/drivers/mmap-test$ make
#arm-linux-gnueabi-gcc test.c -o mmap-tst
#:/local/mnt/workspace/qemu/linux-4.14.217/drivers/mmap-test$ cp mmap4.ko ../../../busybox/root/rootfs/mmap-test/
#:/local/mnt/workspace/qemu/linux-4.14.217/drivers/mmap-test$ cp mmap-tst ../../../busybox/root/rootfs/mmap-test/
#:/local/mnt/workspace/qemu/busybox/root$ ps -a
#:/local/mnt/workspace/qemu/busybox/root$ kill 26704
#:/local/mnt/workspace/qemu/busybox/root$ ./mount-rootfs.sh
#== equal to mkdir etc ; cd /etc ; mkdir init.d ; cd init.d ; touch rcS ;chmod a+x rcS
#:/local/mnt/workspace/qemu/busybox/root$ ./boot.sh
#== equal to
#qemu-system-arm -M vexpress-a9 \
#    -m 512M \
#    -kernel zImage \
#    -dtb vexpress-v2p-ca9.dtb \
#    -nographic \
#    -append "root=/dev/mmcblk0 rw console=ttyAMA0" \
#    -sd rootfs.ext3
# in the qemu
# # mount -t proc none /proc
#ls
# cd mmap-test
#/mmap-test # insmod mmap4.ko
#lsmod

#/mmap-test # ./mmap-tst

