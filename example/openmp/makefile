# compile each cpp file into separate executable

SHELL = /bin/sh

CXX = g++
INC = -I./ -I../../include -I/opt/version/latest/zergtool/include -I$(HOME)/include
LDFLAGS = -L./
LDLIBS = -fopenmp -pthread
CXXFLAGS = -std=c++11 -Wall -O3 -fno-rtti -pedantic -Werror ${INC}

all: $(patsubst %.cpp, %, $(wildcard *.cpp))
%: %.o
	${CXX} ${CXXFLAGS} $< -o $@ $(LDFLAGS) $(LDLIBS)

%.o: %.cpp Makefile
	${CXX} -c ${CXXFLAGS} $< -o $@

clean:
	-rm -f *.o *_omp
