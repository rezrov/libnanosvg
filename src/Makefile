rm nanosvg.o nanosvgrast.o
gcc -c -fpic nanosvg.c
gcc -c -fpic nanosvgrast.c
gcc -shared -o libnanosvg.so nanosvg.o nanosvgrast.o
rm pynanosvg.c pynanosvg*.so
python setup.py build_ext -i
# gcc -c -fpic -I/usr/include/python3.3 -I. pynanosvg.c
# gcc -shared -o pynanosvg.so pynanosvg.o

