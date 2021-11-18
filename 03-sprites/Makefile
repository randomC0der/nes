CC = ca65
LD = ld65

src_files = $(wildcard *.asm)
obj_files = $(src_files:.asm=.o)

all: $(src_files)
	$(LD) $(obj_files) -C nes.cfg -o sprites.nes

$(filter %.asm,$(src_files)): %.asm: %.o
	$(CC) $@

%.o:
# Mind the tab
	

clean: $(wildcard *.o) $(wildcard *.nes)
ifeq ($(OS),Windows_NT)
	for %%i in ($^) do del %%i
else
	rm -f $^
endif
