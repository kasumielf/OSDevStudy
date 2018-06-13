all: BootLoader Disk.img

BootLoader:
	@echo
	@echo ======== Build BootLoader ========
	@echo 

	make -C 00.BootLoader

	@echo
	@echo ======== Build BootLoader Complete ========
	@echo 

Kernel32:
	@echo
	@echo ======== Build Kernel32 ========
	@echo 

	make -C 01.Kernel32

	@echo
	@echo ======== Build Kernel32 Complete ========
	@echo 

Disk.img: 00.BootLoader/Bootloader.bin Kernel32
	@echo
	@echo ======== Build Disk Image ========
	@echo 

	cat 00.BootLoader/BootLoader.bin 01.Kernel32/VirtualOS.bin > Disk.img

	@echo
	@echo ======== Build Disk Image Complete ========
	@echo 
	
clean:
	make -C 00.BootLoader clean
	make -C 01.Kernel32 clean
	rm -f Disk.img