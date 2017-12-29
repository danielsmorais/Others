CPPUNIT_PATH=/diretorio_onde_esta_o_cppunit
INCLUDE_DIR=$CPPUNIT_PATH)/include
LIB_DIR=$(CPPUNIT_PATH)/lib
LIBS=-lcppunit
CPPFLAGS=-I$(INCLUDE_DIR)
LDFLAGS=-L$(LIB_DIR) $(LIBS)
CPPSOURCES = $(wildcard *.cpp)
all: ftest
ftest: $(CPPSOURCES:.cpp=.o)
	@echo Criando arquivo execut´avel: $@
	@g++ -o $@ $^ $(LDFLAGS)

%.o: %.cpp
	@echo Compilando arquivo objeto: $@
	@g++ -c $< $(CPPFLAGS) -o $@
clean
	@echo Limpando arquivos
	-@rm -f *.o ftest *~
remade:
	$(MAKE) clean
	$(MAKE)
-include $(CPPSOURCES:.cpp=.d)
%.d: %.cpp
	@g++ $< -MM -MT ’$*.o $*.d ’ -MD $(CPPFLAGS)
