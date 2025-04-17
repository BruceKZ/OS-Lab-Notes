# PintOS Labs Note

## 0. Before Start

### 0x01 Environment Setting

Since the server's environment has already been configured, we'll skip the part about configuring the environment here.

### 0x02 Root directory shortcut

In the following, the root directory of this project is replaced by `@` (i.e. the path to this file should be `@/README.md` ) 

### 0x03 Source Code

PintOS Source Code can be downloaded from `@/SourceCode/pintos0.tar.gz` .

To extract the source code, run

```shell
tar xzvf pintos0.tar.gz
```

### 0x04 Start the virtual machine

To start the virtual machine, do:

```shell
cd pintos0 # go into folder extracted from the .tar.gz archive
```

```shell
vagrant up # start the VM. this will take a while the first time...
```

### 0x05 Connect to virtual machine

Connect to vagrant

```shell
vagrant ssh # ssh into the running virtual machine
```

### 0x06 Stop the virtual machine

To stop the virtual machine, you have two options:

```shell
vagrant suspend # save the machine state to disk and suspend (uses more disk space)
```

```shell
vagrant halt # shutdown the machine (takes more time to boot up again)
```

### 0x07 Compiling & running PintOS

Compiling and running PintOS is done from inside the virtual machine.
To check that everything is working as intended, ssh into the VM and run:

```shell
cd /pintos-env/pintos/threads   # go into the threads project folder
make clean                      # clear old binaries if any
make                            # compile pintos
make check                      # run the unit tests
```

After running make check, you should see that 20 of 27 tests failed.
Throughout the course, we will implement new functionalities and some of these tests will start passing.

### 0x08 Running Tests
There are many tests. See pintos/tests/threads. To run a single test, do:

```shell
cd /pintos-env/pintos/threads
pintos -v -- run alarm-single   # run the alarm-single test
To run all tests in one of the project folders (threads, userprog, vm, or filesys):
```

```shell
cd /pintos-env/pintos/threads   # go into one of the projects
make
make check
```

### 0x09 Debugging
Debugging will also be done from inside the virtual machine. We are going to use two terminals, both connected to the VM.

In the first terminal, start a test in debug mode:

```shell
cd /pintos-env/pintos/threads
pintos --gdb -- run alarm-single   # start in debug mode and wait for a connection
```

In the second terminal, start GDB and connect to the running PintOS:

```shell
cd /pintos-env/pintos/threads
pintos-gdb build/kernel.o          # start gdb
gdb> debugpintos                   # connect to the running pintos
```

The debugpintos command is just a macro for:

```shell
gdb> target remote localhost:1234  # connect to the running pintos
```

Appendix E in the PintOS documentation (`@/PDF/pintos_documentation`) explains how to use GDB and other debugging techniques.

## 1. Project0: Lists






















