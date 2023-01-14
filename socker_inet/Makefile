CC := g++
CCFLAGS := -g -pthread

# ./client ./server
SUBDIRS := $(wildcard */)

CCFLAGS += $(addprefix -I , $(SUBDIRS))

OUTPUTS := ./client/client.out ./server/server.out

%.o : %.cpp
	$(CC) $(CCFLAGS) -c $< -o $@

%.out : %.o
	$(CC) $(CCFLAGS) $< -o $@

.PHONY :  all clean

all : $(OUTPUTS)

clean :
	for dir in $(SUBDIRS) ; do \
		rm -rf $$dir*.o ; \
		rm -rf $$dir*.out ; \
	done
