# PintOS Labs Note

## 0. Before Start

### 0x01

Since the server's environment has already been configured, we'll skip the part about configuring the environment here.

### 0x02

In the following, the root directory of this project is replaced by `@` (i.e. the path to this file should be `@/README.md` ) 

### 0x03

PintOS Source Code can be downloaded from `@/SourceCode/pintos0.tar.gz` .

To extract the source code, run

```shell
tar xzvf pintos0.tar.gz
```

### 0x04

To start the virtual machine, do:

```shell
cd pintos0 # go into folder extracted from the .tar.gz archive
```

```shell
vagrant up # start the VM. this will take a while the first time...
```

### 0x05

Connect to vagrant

```shell
vagrant ssh # ssh into the running virtual machine
```

### 0x06

To stop the virtual machine, you have two options:
```shell
vagrant suspend # save the machine state to disk and suspend (uses more disk space)
```

```shell
vagrant halt # shutdown the machine (takes more time to boot up again)
```



