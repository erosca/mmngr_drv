CFILES = mmngr_drv.c

obj-m += mmngr.o
mmngr-objs := $(CFILES:.c=.o)

ccflags-y	+= -D$(MMNGR_CONFIG)
ccflags-y	+= -D$(MMNGR_SSP_CONFIG)
ccflags-y	+= -D$(MMNGR_IPMMU_PMB_CONFIG)
ccflags-y	+= -I$(KERNELSRC)/include

all:
	$(CP) ../include/mmngr_public.h $(KERNELSRC)/include
	$(CP) ../include/mmngr_private.h $(KERNELSRC)/include
	$(CP) ../include/mmngr_private_cmn.h $(KERNELSRC)/include
	$(CP) ../include/mmngr_public_cmn.h $(KERNELSRC)/include
	$(CP) ../include/mmngr_private_cmn.h $(INCSHARED)
	$(CP) ../include/mmngr_public_cmn.h $(INCSHARED)
	make -C $(KERNELSRC) M=$(PWD) modules
clean:
	make -C $(KERNELSRC) M=$(PWD) clean
	rm -f $(KERNELSRC)/include/mmngr_public.h
	rm -f $(KERNELSRC)/include/mmngr_private.h
	rm -f $(KERNELSRC)/include/mmngr_private_cmn.h
	rm -f $(KERNELSRC)/include/mmngr_public_cmn.h
