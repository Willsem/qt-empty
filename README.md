# Empty template for qt c++ projects

## Build with make

```bash
$ mkdir build && cd build
$ cmake -S .. -B .
$ make
$ ./helloworld
```

## Build with Ninja (faster)

[Ninja](https://github.com/ninja-build/ninja) needs

```bash
$ mkdir build && cd build
$ cmake -S .. -B . -G Ninja
$ ninja
$ ./helloworld
```
