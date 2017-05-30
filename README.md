xptMiner
========

This is a Riecoin (RIC)-focused release built upon xptMiner.  It
contains only a Riecoin miner - for the reference implementation
of xptMiner, please see https://github.com/jh000/xptMiner

This build supports Linux and Windows, the latter via the Makefile.mingw.

Authors:  xptMiner was written by jh00;
          This version is based upon the Unix port by Clintar
          The riecoin mining core was rewritten by dga based upon jh00's version.

Some instructions to get started


PREREQUISITES 
=============
CentOS:
sudo yum groupinstall "Development Tools"
sudo yum install openssl openssl-devel openssh-clients gmp gmp-devel gmp-static git wget

Ubuntu:
sudo apt-get -y install build-essential m4 openssl libssl-dev git libjson0 libjson0-dev libcurl4-openssl-dev wget

BUILDING
========

PREREQUISITES 
Ubuntu: sudo apt-get -y install build-essential m4 openssl libssl-dev git libjson0 libjson0-dev libcurl4-openssl-dev wget libjansson-dev

wget http://mirrors.kernel.org/gnu/gmp/gmp-6.0.0a.tar.bz2

tar xjvf gmp-6.0.0a.tar.bz2

cd gmp-6.0.0

./configure --enable-cxx

make -j4 && sudo make install

cd ..
git clone https://github.com/XpoolX/StratumRieMiner

cd StratumRieMiner

LD_LIBRARY_PATH=/usr/local/lib

make -j4

Optionally run:
./build_allme.riecoinworkername -p workerpassword


if you get illegal instruction try this

make clean
LD_LIBRARY_PATH=/usr/local/lib make -j4 -f Makefile.mtune

and run it again. If it still gets a segfault, (let me know, please) and try this

make clean
LD_LIBRARY_PATH=/usr/local/lib make -j4 -f Makefile.nomarch


This has a default 2% donation that can be set using the -d option (-d 2.5 would be 2.5% donation)
