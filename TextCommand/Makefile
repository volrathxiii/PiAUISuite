BLDDEF  = -D'BUILDTS="$(shell date +"%y%m%d %H:%M:%S %z")"'

#Set Architecture
ARCH := arm-v7
DEVEL := rel
LIBS := -lcurl -lboost_regex 

#Compilers
ifeq ($(ARCH),arm-v7)
CC := g++-4.8 -mcpu=cortex-a7 -mfpu=neon-vfpv4 -mfloat-abi=hard
else
ifeq ($(ARCH),arm)
CC := g++ -mcpu=arm1176jzf-s -mfpu=vfp -mfloat-abi=hard
else
ifeq ($(ARCH),x86)
CC := g++ -m32
OUTPUT := x86/
else
CC := g++
OUTPUT := x64/
endif
endif
endif

#devel flags
ifeq ($(BUILD),devel)
FLAGS := -g -Wall
else
FLAGS := -O3
endif

gtextcommand: gtextcommand.cpp gvoice.cpp gvoice.h
	$(CC) $(BLDDEF) $(FLAGS) $(LIBS) -o $(addprefix $(OUTPUT), gtextcommand) $(addprefix $(OUTPUT), gvoice.o) gtextcommand.cpp

gvapi: gvapi.cpp gvoice.cpp gvoice.h
	$(CC) $(BLDDEF) $(FLAGS) $(LIBS) -o $(addprefix $(OUTPUT), gvapi) $(addprefix $(OUTPUT), gvoice.o) gvapi.cpp

gvoice: gvoice.cpp gvoice.h
	$(CC) $(BLDDEF) $(FLAGS) $(LIBS) -c -o $(addprefix $(OUTPUT), gvoice.o) gvoice.cpp

clean:
	rm *.o gtextcommand gvapi 2>/dev/null

install: gtextcommand
	install gtextcommand /usr/bin/gtextcommand
	install gtextcommand /usr/bin/gvapi
