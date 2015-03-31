# TLexScan 
TLexScan version 0.10 -The whole area of LAN examination Scaner  
Local area network scaner for linux from slank  

## Description
TLexScan looks for all devices  in the LAN, 
you can create a list by examining their IP and MAC.  
The survival confirmation of the device, I am using the arp.
User will be able to know the information of the LAN 
that is quickly and easily and safely your connection .  

## Demo
 please see this video
 http://youtu.be/X75uHbJuGr4


## VS.
 Fing <http://www.overlooksoft.com/fing>  

## Requirement
 libpcap <http://www.tcpdump.org>  
 gcc (Ubuntu 4.8.2-19ubuntu1) 4.8.2 <http://gcc.gnu.org>  
 GNU Make 3.81 <http://www.gnu.org/software/make>  

## Usage

	usage: ./tlex.out	[-i interface] [-c loop_count]
				[-t timeout] [-p filename] [-s filename]
				[-f filename] [-n noverbose]

		-i	select interface
		-c	loop count of send_arp_to_alladdr
		-t	timeout
		-f	select logfile if file not found then make newfile
		-p	print logfile only
		-s	sort logfile only
		-n	no verbose


## Contribution
1. Fork it ( $ git clone http://github.com/slank-dev/tlexscan.git )
2. Create your feature branch (git checkout -b my-new-feature)
3. Commit your changes (git commit -am 'Add some feature')
4. Push to the branch (git push origin my-new-feature)


## Instration
	 
	$ make
	g++    -c -o main.o main.cc
	g++    -c -o addr.o addr.cc
	g++    -c -o arp.o arp.cc
	g++    -c -o scanLan.o scanLan.cc
	g++    -c -o util.o util.cc
	g++  main.o addr.o arp.o scanLan.o util.o -o tlex.out -Wall -lpcap
	

	$ sudo ./tlex.out -i eth0
	Starting TLex 0.1.0 ( http://www.tlex.org ) 02:27:54
	--------------------------------
	Interface    :  eth0           
	scan_count   :  1              
	timeout      :  5   sec  
	logfile      :  test.log       
	verbose info :  1              
	--------------------------------
	 * [ARPSCAN] start
	 - Add new log at 02:27:55 [192.168.179.6, 80:e6:50:17:18:46, 112437995]
	 - Add new log at 02:27:55 [192.168.179.1, a2:12:42:17:d8:8f, 28551988]
	 - Add new log at 02:27:55 [192.168.179.15, b8:27:eb:34:6b:92, 263433147]
	 - Add new log at 02:27:55 [192.168.179.4, 84:b1:53:6a:2f:20, 78883585]
	 * [ARPSCAN] finish

	  +-------------------------------------------------------------------------+
	  |  IP address         |  MAC address        |  Bender         |  Update   |
	  +-------------------------------------------------------------------------+
	  |  192.168.179.1   	|  a2:12:42:17:d8:8f  | not-found      	|  02:27:55 |
	  |  192.168.179.4   	|  84:b1:53:6a:2f:20  | Apple      	|  02:27:55 |
	  |  192.168.179.6   	|  80:e6:50:17:18:46  | Apple      	|  02:27:55 |
	  |  192.168.179.15   	|  b8:27:eb:34:6b:92  | Raspberry      	|  02:27:55 |
	  +-------------------------------------------------------------------------+

	TLex done: scan finished in 5.824 sec 
	$

## Licence
 
	Copyright (C) 2014-2015 Hiroki Shirokura <mail: slank.dev@gmail.com>

	TLexScan is free software: you can redistribute it and/or modify
	it under the terms of the GNU General Public License as published by
	the Free Software Foundation, either version 3 of the License, or
	(at your option) any later version.

	TLexScan is distributed in the hope that it will be useful,

	but WITHOUT ANY WARRANTY; without even the implied warranty of
	MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
	GNU General Public License for more details.

	You should have received a copy of the GNU General Public License
	along with this program.  
	If not, see <http://slankdev.wordpress.com>.
	slank (Hiroki Shirokura) <mail: slank.dev@gmail.com>