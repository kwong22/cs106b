# Makefile for name_hash
#****************************************************************

PROGRAM = name_hash
SOURCES = name_hash.cpp
OBJECTS = $(SOURCES:.cpp=.o)

ROOTPATH = ../../cpplib
CPPOPTIONS = -I$(ROOTPATH)/include -fvisibility-inlines-hidden -std=c++11
LDOPTIONS = -L$(ROOTPATH)/lib -static-libstdc++
LIB = -lStanfordCPPLib

# ***************************************************************
# Entry to bring the package up to date
#    The "make all" entry should be the first real entry

all: $(PROGRAM) spl.jar

spl.jar:
	@ln -s $(ROOTPATH)/java/spl.jar

$(PROGRAM): $(OBJECTS)
	g++ -o $(PROGRAM) $(LDOPTIONS) $(OBJECTS) $(LIB)

$(OBJECTS): $(SOURCES) Makefile $(ROOTPATH)/lib/libStanfordCPPLib.a
	g++ -c $(CPPOPTIONS) $(SOURCES)


# ***************************************************************
# Standard entries to remove files from the directories
#    tidy  -- eliminate unwanted files
#    clean -- delete derived files in preparation for rebuild

tidy:
	rm -f ,* .,* *~ core a.out *.err

clean scratch: tidy
	rm -f *.o *.a $(PROGRAM) $(OBJECTS) spl.jar
