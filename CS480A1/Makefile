#Makefile

#.RECIPEPREFIX +=

# Specify compiler
CC = g++
# Compiler flags, if you want debug info, add -g
CCFLAGS = -std=c++11 -g3 -Wall -c
CFLAGS = -g3 -c

# object files
OBJS = pageTableLevel.o tracereader.o main.o log.o pageTable.o

# Program name
PROGRAM = pagetrace

#Default target
all: $(PROGRAM)

# The program depends upon its object files
$(PROGRAM) : $(OBJS)
	$(CC) -o $(PROGRAM) $(OBJS)

main.o : main.cpp pageTable.h pageTableLevel.h tracereader.h log.h
	$(CC) $(CCFLAGS) main.cpp

pageTableLevel.o : pageTableLevel.cpp pageTableLevel.h
	$(CC) $(CCFLAGS) pageTableLevel.cpp

pageTable.o : pageTable.cpp pageTable.h
	$(CC) $(CCFLAGS) pageTable.cpp

tracereader.o : tracereader.c tracereader.h
	$(CC) $(CFLAGS) tracereader.c

log.o : log.c log.h
	$(CC) $(CFLAGS) log.c

# Once things work, people frequently delete their object files.
# If you use "make clean", this will do it for you.
# As we use gnuemacs which leaves auto save files termintating
# with ~, we will delete those as well.
clean :
	rm -rf $(OBJS) *~ $(PROGRAM)

.PHONY: clean all