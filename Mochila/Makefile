SYSTEM     = x86_sles10_4.1
LIBFORMAT  = static_pic

#mude os dois caminhos abaixo para os caminhos onde o CPLEX foi instalado no seu computador
CPLEXDIR      = /opt/ibm/ILOG/CPLEX_Studio_Preview124/cplex
CONCERTDIR    = /opt/ibm/ILOG/CPLEX_Studio_Preview124/concert

CCC = g++ -O0

CCOPT = -m32 -O -fPIC -fno-strict-aliasing -fexceptions -DNDEBUG -DIL_STD

CPLEXLIBDIR   = $(CPLEXDIR)/lib/$(SYSTEM)/$(LIBFORMAT)
CONCERTLIBDIR = $(CONCERTDIR)/lib/$(SYSTEM)/$(LIBFORMAT)

CCLNFLAGS = -L$(CPLEXLIBDIR) -lilocplex -lcplex -L$(CONCERTLIBDIR) -lconcert -m32 -lm -pthread

CONCERTINCDIR = $(CONCERTDIR)/include
CPLEXINCDIR   = $(CPLEXDIR)/include

CCFLAGS = $(CCOPT) -I$(CPLEXINCDIR) -I$(CONCERTINCDIR) 

main: main.o
	$(CCC) $(CCFLAGS) main.o -o main $(CCLNFLAGS)
main.o: main.cpp
	$(CCC) -c $(CCFLAGS) main.cpp -o main.o
