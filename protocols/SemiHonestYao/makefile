INC               =  -I../../../boost_1_60_0 -I../../lib -I../../install/include -I../../lib/OTExtensionBristol -I../../build
CXX               = g++ -std=c++11 $(INC) -O3 -Wall -Wno-unused-function -Wno-unused-variable
LIBS              =  -L../../install/lib -L../../../boost_1_60_0/stage/lib
LINKER_OPTIONS    =  ../../scapi.a ../../install/lib/libOTExtensionBristol.a ../../install/lib/libsimpleot.a $(LIBS) -lcrypto -ldl -lboost_log -lboost_system -lboost_thread -lpthread -lssl -lgmp -lOTExtension -lMaliciousOTExtension -lrt
CPP_OPTIONS       = -std=c++11 $(INC) -O3 -Wall -Wno-unused-function
OBJS              = YaoParties.o

all: Yao.out

Yao.out: $(OBJS)
	$(CXX) App1.cpp -o $@ $(OBJS) $(LINKER_OPTIONS)

YaoParties.o: YaoParties.cpp
	$(CXX) -c -maes -mpclmul $< -o $@

clean:
	rm -f *.o
	rm -f *.out