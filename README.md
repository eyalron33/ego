# ego
## Build and test for Linux

To make and test, run

~~~~
make test
~~~~

To make sample programs, run

~~~~
make sample_test
~~~~

To compile webID
~~~~
g++ -g3 -Wall -Wextra -Wformat=2 -Wcast-qual -Wcast-align -Wwrite-strings -Wfloat-equal -Wpointer-arith -m64 -I include -I test -I ../xbyak -I ../cybozulib/include -fomit-frame-pointer -DNDEBUG -Ofast -march=native  -fPIC -std=c++11 -I../mcl/include -D"MCLBN_FP_UNIT_SIZE=4" -c eyal/webID.cpp -o obj/webID.o -MMD -MP -MF obj/webID.d

g++ obj/webID.o -o bin/webID lib/libbls.a lib/libbls384.a -lmcl -L../mcl/lib -lrt -lgmp -lgmpxx -lcrypto -m64  -lpthread
~~~~
