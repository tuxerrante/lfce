Example: stress-ng --cpu 8 --io 4 --vm 2 --vm-bytes 128M --fork 4 --timeout 10s
-c N, --cpu N              start N workers spinning on sqrt(rand())
-i N, --io N               start N workers spinning on sync()
-m N, --vm N               start N workers spinning on anonymous mmap
--vm-bytes N         allocate N bytes per vm worker (default 256MB)
-f N, --fork N             start N workers spinning on fork() and exit()
-t N, --timeout T          timeout after T seconds

Generally stress-ng is used to perform different tests.

Packages required for building packages. 
sudo apt-get install dh-make fakeroot build-essential

Commands used in building packages. 
1) tar

Examples:
  tar -cf archive.tar foo bar  # Create archive.tar from files foo and bar.
  tar -tvf archive.tar         # List all files in archive.tar verbosely.
  tar -xf archive.tar          # Extract all files from archive.tar.
Use tar -xzvf and -czvf and -tvf (z for gzip). 

2) dh_make

-> WORK
	-> cpphelloworld-1.0/
		-> 	dh_make -f ../cpphelloworld-1.0.tar.gz
	-> cpphelloworld-1.0.tar.gz


3) dpkg-buildpackage

-> WORK
	-> cpphelloworld-1.0
		-> dpkg-buildpackage -uc -us
	-> cpphelloworld-1.0.tar.gz
  -us            unsigned source package.
  -uc            unsigned .changes file.


4) dpkg (--contents, --install or -i, --remove or -r)  

## Summary
#### Example 1
```sh
apt install dh-make

git clone https://github.com/streadway/hello-debian
cd hello-debian
git archive master | gzip > ../hello-debian_0.0.1.tar.gz

dh_make -p hello-debian_0.0.1 -f ../hello-debian_0.0.1.tar.gz
dpkg-buildpackage -uc -us
dpkg --install ../hello-debian_0.0.2-1_amd64.deb

cd
hello-world 
```

#### Example 2
```
tar -czvf cpphelloworld-1.0.tar.gz cpphelloworld-1.0/
mkdir WORK
mv cpphelloworld-1.0.tar.gz WORK/
cd WORK
tar -xzvf cpphelloworld-1.0.tar.gz
cd cpphelloworld-1.0/
dh_make -f ../cpphelloworld-1.0.tar.gz
dpkg-buildpackage -uc -us
dpkg --contents ../cpphelloworld_1.0-1_amd64.deb
sudo dpkg --install ../*.deb
dpkg --remove cpphelloworld
```

My Example Makefile 

all:
        g++ CppHelloWorld.cpp -o CppHelloWorld
install:
        install -d $(DESTDIR)/usr/bin
        install CppHelloWorld $(DESTDIR)/usr/bin
clean:
        rm -f CppHelloWorld
~                              
