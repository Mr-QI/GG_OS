OBJECTS = boot.bin loader.bin 
NA 		= nasm

all: $(OBJECTS)

$(OBJECTS): %.bin:%.asm
	$(NA) $< -o $@	

exec:
	# dd if=boot.bin of=boot.img bs=512 count=1 conv=notrunc;
	#umount ../mountdir
	mount boot.img ../mountdir/ -t vfat -o loop;\
	cp loader.bin ../mountdir/;\
	sync;
	# bochs -f ../bochs-2.6.9/.bochsrc

.PHONY clean:
	rm -rf *.bin; umount ../mountdir; cd ../mountdir; rm *.bin 	
	
 