# Set up info for C++ implicit rule
CC = mpicc
CCFLAGS = -lm
CPPFLAGS =
LDFLAGS =
PROJECTNAME = CS4301_program3
SRCS = program3.c
EXEC = program3
OMP = program3omp
OMPFLAGS = -fopenmp

MPI = mpirun
MPIFLAGS = -n 4
ARGS = 100 DEBUG

# For Testing

N1  = -n 2
N2  = -n 3
N3  = -n 4
N4  = -n 5
N5  = -n 6
N6  = -n 7
N7  = -n 8
N8  = -n 9
N9  = -n 10
N10 = -n 11

T1  = 100
T2  = 1000
T3  = 5000
T4  = 10000
T5  = 50000
T6  = 100000
T7  = 500000            #500k
T8  = 1000000           #1M
T9  = 50000000          #50M
T10 = 100000000         #100M
T11 = 5000000000        #500M
T12 = 10000000000       #1B
# ======================================================
# ======================================================

OBJS = $(SRCS:c=o)

all: $(EXEC) $(OMP)

omp: $(OMP)

debug: all debug_test

test: all all_tests

debug_test:
        clear
        $(MPI) $(MPIFLAGS) ./$(EXEC) $(ARGS)

simple_test:
        clear
        $(MPI) $(N1) ./$(EXEC) $(T1)

clean:
        rm -f $(OBJS) *.d *~ \#* $(EXEC)

Makefile: $(SRCS:.c=.d)

# Pattern for .d files.
%.d:%.c
        @echo Updating .d Dependency File
        @set -e; rm -f $@; \
        $(CC) -MM $(CPPFLAGS) $< > $@.$$$$; \
        sed 's,\($*\)\.o[ :]*,\1.o $@ : ,g' < $@.$$$$ > $@; \
        rm -f $@.$$$$

#  This is a rule to link the files.  Pretty standard
$(EXEC): $(OBJS)
        $(CC) -o $(EXEC) $(CCFLAGS) $(OBJS)

$(OMP): $(OBJS)
        $(CC) -o $(OMP) $(CCFLAGS) $(OMPFLAGS) $(OBJS)

# Backup Target
backup: clean
        @mkdir -p ~/backups; chmod 700 ~/backups
        @$(eval CURDIRNAME := $(shell basename `pwd`))
        @$(eval MKBKUPNAME := ~/backups/$(PROJECTNAME)-$(shell date +'%Y.%m.%d-%H:%M:%S').tar.gz)
        @echo
        @echo Writing Backup file to: $(MKBKUPNAME)
        @echo
        @-tar zcfv $(MKBKUPNAME) ../$(CURDIRNAME)
        @chmod 600 $(MKBKUPNAME)
        @echo
        @echo Done!


# Include the dependency files
-include $(SRCS:.c=.d)

all_tests:
        $(MPI) $(N1) ./$(EXEC) $(T1)
        $(MPI) $(N1) ./$(EXEC) $(T2)
        $(MPI) $(N1) ./$(EXEC) $(T3)
        $(MPI) $(N1) ./$(EXEC) $(T4)
        $(MPI) $(N1) ./$(EXEC) $(T5)
        $(MPI) $(N1) ./$(EXEC) $(T6)
        $(MPI) $(N1) ./$(EXEC) $(T7)
        $(MPI) $(N1) ./$(EXEC) $(T8)
        $(MPI) $(N1) ./$(EXEC) $(T9)
        $(MPI) $(N1) ./$(EXEC) $(T10)
        $(MPI) $(N2) ./$(EXEC) $(T1)
        $(MPI) $(N2) ./$(EXEC) $(T2)
        $(MPI) $(N2) ./$(EXEC) $(T3)
        $(MPI) $(N2) ./$(EXEC) $(T4)
        $(MPI) $(N2) ./$(EXEC) $(T5)
        $(MPI) $(N2) ./$(EXEC) $(T6)
        $(MPI) $(N2) ./$(EXEC) $(T7)
        $(MPI) $(N2) ./$(EXEC) $(T8)
        $(MPI) $(N2) ./$(EXEC) $(T9)
        $(MPI) $(N2) ./$(EXEC) $(T10)
        $(MPI) $(N3) ./$(EXEC) $(T1)
        $(MPI) $(N3) ./$(EXEC) $(T2)
        $(MPI) $(N3) ./$(EXEC) $(T3)
        $(MPI) $(N3) ./$(EXEC) $(T4)
        $(MPI) $(N3) ./$(EXEC) $(T5)
        $(MPI) $(N3) ./$(EXEC) $(T6)
        $(MPI) $(N3) ./$(EXEC) $(T7)
        $(MPI) $(N3) ./$(EXEC) $(T8)
        $(MPI) $(N3) ./$(EXEC) $(T9)
        $(MPI) $(N3) ./$(EXEC) $(T10)
        $(MPI) $(N4) ./$(EXEC) $(T1)
        $(MPI) $(N4) ./$(EXEC) $(T2)
        $(MPI) $(N4) ./$(EXEC) $(T3)
        $(MPI) $(N4) ./$(EXEC) $(T4)
        $(MPI) $(N4) ./$(EXEC) $(T5)
        $(MPI) $(N4) ./$(EXEC) $(T6)
        $(MPI) $(N4) ./$(EXEC) $(T7)
        $(MPI) $(N4) ./$(EXEC) $(T8)
        $(MPI) $(N4) ./$(EXEC) $(T9)
        $(MPI) $(N4) ./$(EXEC) $(T10)
        $(MPI) $(N5) ./$(EXEC) $(T1)
        $(MPI) $(N5) ./$(EXEC) $(T2)
        $(MPI) $(N5) ./$(EXEC) $(T3)
        $(MPI) $(N5) ./$(EXEC) $(T4)
        $(MPI) $(N5) ./$(EXEC) $(T5)
        $(MPI) $(N5) ./$(EXEC) $(T6)
        $(MPI) $(N5) ./$(EXEC) $(T7)
        $(MPI) $(N5) ./$(EXEC) $(T8)
        $(MPI) $(N5) ./$(EXEC) $(T9)
        $(MPI) $(N5) ./$(EXEC) $(T10)
        $(MPI) $(N6) ./$(EXEC) $(T1)
        $(MPI) $(N6) ./$(EXEC) $(T2)
        $(MPI) $(N6) ./$(EXEC) $(T3)
        $(MPI) $(N6) ./$(EXEC) $(T4)
        $(MPI) $(N6) ./$(EXEC) $(T5)
        $(MPI) $(N6) ./$(EXEC) $(T6)
        $(MPI) $(N6) ./$(EXEC) $(T7)
        $(MPI) $(N6) ./$(EXEC) $(T8)
        $(MPI) $(N6) ./$(EXEC) $(T9)
        $(MPI) $(N6) ./$(EXEC) $(T10)
        $(MPI) $(N7) ./$(EXEC) $(T1)
        $(MPI) $(N7) ./$(EXEC) $(T2)
        $(MPI) $(N7) ./$(EXEC) $(T3)
        $(MPI) $(N7) ./$(EXEC) $(T4)
        $(MPI) $(N7) ./$(EXEC) $(T5)
        $(MPI) $(N7) ./$(EXEC) $(T6)
        $(MPI) $(N7) ./$(EXEC) $(T7)
        $(MPI) $(N7) ./$(EXEC) $(T8)
        $(MPI) $(N7) ./$(EXEC) $(T9)
        $(MPI) $(N7) ./$(EXEC) $(T10)
        $(MPI) $(N8) ./$(EXEC) $(T1)
        $(MPI) $(N8) ./$(EXEC) $(T2)
        $(MPI) $(N8) ./$(EXEC) $(T3)
        $(MPI) $(N8) ./$(EXEC) $(T4)
        $(MPI) $(N8) ./$(EXEC) $(T5)
        $(MPI) $(N8) ./$(EXEC) $(T6)
        $(MPI) $(N8) ./$(EXEC) $(T7)
        $(MPI) $(N8) ./$(EXEC) $(T8)
        $(MPI) $(N8) ./$(EXEC) $(T9)
        $(MPI) $(N8) ./$(EXEC) $(T10)
        $(MPI) $(N9) ./$(EXEC) $(T1)
        $(MPI) $(N9) ./$(EXEC) $(T2)
        $(MPI) $(N9) ./$(EXEC) $(T3)
        $(MPI) $(N9) ./$(EXEC) $(T4)
        $(MPI) $(N9) ./$(EXEC) $(T5)
        $(MPI) $(N9) ./$(EXEC) $(T6)
        $(MPI) $(N9) ./$(EXEC) $(T7)
        $(MPI) $(N9) ./$(EXEC) $(T8)
        $(MPI) $(N9) ./$(EXEC) $(T9)
        $(MPI) $(N9) ./$(EXEC) $(T10)
        $(MPI) $(N10) ./$(EXEC) $(T1)
        $(MPI) $(N10) ./$(EXEC) $(T2)
        $(MPI) $(N10) ./$(EXEC) $(T3)
        $(MPI) $(N10) ./$(EXEC) $(T4)
        $(MPI) $(N10) ./$(EXEC) $(T5)
        $(MPI) $(N10) ./$(EXEC) $(T6)
        $(MPI) $(N10) ./$(EXEC) $(T7)
        $(MPI) $(N10) ./$(EXEC) $(T8)
        $(MPI) $(N10) ./$(EXEC) $(T9)
        $(MPI) $(N10) ./$(EXEC) $(T10)

test_11:
        $(MPI) $(N1) ./$(EXEC) $(T11)
        $(MPI) $(N2) ./$(EXEC) $(T11)
        $(MPI) $(N3) ./$(EXEC) $(T11)
        $(MPI) $(N4) ./$(EXEC) $(T11)
        $(MPI) $(N5) ./$(EXEC) $(T11)
        $(MPI) $(N6) ./$(EXEC) $(T11)
        $(MPI) $(N7) ./$(EXEC) $(T11)
        $(MPI) $(N8) ./$(EXEC) $(T11)
        $(MPI) $(N9) ./$(EXEC) $(T11)
        $(MPI) $(N10) ./$(EXEC) $(T11)
test_12:
        $(MPI) $(N1) ./$(EXEC) $(T12)
        $(MPI) $(N2) ./$(EXEC) $(T12)
        $(MPI) $(N3) ./$(EXEC) $(T12)
        $(MPI) $(N4) ./$(EXEC) $(T12)
        $(MPI) $(N5) ./$(EXEC) $(T12)
        $(MPI) $(N6) ./$(EXEC) $(T12)
        $(MPI) $(N7) ./$(EXEC) $(T12)
        $(MPI) $(N8) ./$(EXEC) $(T12)
        $(MPI) $(N9) ./$(EXEC) $(T12)
        $(MPI) $(N10) ./$(EXEC) $(T12)