# openmp-test
Instructions and codes to setup and test OpenMP on Mac OSX.

Setting up environment
1. Install XCode Command Line Tools
2. Install Homebrew
3. Install OpenMP library from Homebrew
```commandline=bash
brew install libomp
```
4. Check that the gcc, g++ and clang commands are all linking to Apple's clang
```commandline=bash
~ % gcc --version
Apple clang version 15.0.0 (clang-1500.1.0.2.5)
Target: arm64-apple-darwin23.2.0
Thread model: posix
InstalledDir: /Library/Developer/CommandLineTools/usr/bin
```
```commandline=bash
~ % g++ --version
Apple clang version 15.0.0 (clang-1500.1.0.2.5)
Target: arm64-apple-darwin23.2.0
Thread model: posix
InstalledDir: /Library/Developer/CommandLineTools/usr/bin
```
```commandline=bash
~ % clang --version
Apple clang version 15.0.0 (clang-1500.1.0.2.5)
Target: arm64-apple-darwin23.2.0
Thread model: posix
InstalledDir: /Library/Developer/CommandLineTools/usr/bin
```
4. Compile omptest.c
```commandline=bash
clang -Xclang -fopenmp -L/opt/homebrew/opt/libomp/lib -I/opt/homebrew/opt/libomp/include -lomp omptest.c -o omptest
```
5. Test omptest binary
```commandline=bash
~ % ./omptest 
Hello World... from thread = 0
Hello World... from thread = 12
Hello World... from thread = 4
Hello World... from thread = 8
Hello World... from thread = 3
Hello World... from thread = 2
Hello World... from thread = 1
Hello World... from thread = 13
Hello World... from thread = 7
Hello World... from thread = 11
Hello World... from thread = 10
Hello World... from thread = 6
Hello World... from thread = 9
Hello World... from thread = 5
```