# FTP-application
Using socket API to implement a client server network applicaiton - FTP. 
Read ME
----------------------------------------------
Enviroment tested:
----------------------------------------------
1: Python 2.7
2: flip1 and flip3 have been tested.
3: if using flips for both server and client, make sure .c and .py are in different directory...

----------------------------------------------
How to run:
----------------------------------------------
1: let the server on first:

	ftserver.c
	a: run gcc -o server ftserver.c
	b: run server + PORT number

example:
flip1 ~/cs372/prog2 1126$ gcc -o server ftserver.c
flip1 ~/cs372/prog2 1126$ server 22330
flip1 ~/cs372/prog2 1126$ FTP server open on port 22330

2: let the client command then:

	ftclient.py
	a: chmod +x ftclient.py  to change permission 
	b: ftclient.py + SEVER + SEVER PORT + -l | -g + [filename] + Client PORT

example:

flip1 ~/cs372/prog2/client 1055$ chmod +x ftclient.py
flip1 ~/cs372/prog2/client 1056$ ftclient.py flip1.engr.oregonstate.edu 22330 -l 33220
flip1 ~/cs372/prog2/client 1057$ ftclient.py flip1.engr.oregonstate.edu 22331 -g lol.txt 33220


----------------------------------------------
Running example(fully):
----------------------------------------------
STEP 1:==>server

flip1 ~/cs372/prog2 1126$ gcc -o server ftserver.c
flip1 ~/cs372/prog2 1126$ server 22330

STEP 2:==>client
flip1 ~/cs372/prog2/client 1055$ chmod +x ftclient.py
flip1 ~/cs372/prog2/client 1056$ ftclient.py flip1.engr.oregonstate.edu 22330 -l 33220


Client: Control sesssion set up with 128.193.54.168 : 22330
Sending client port to server...(FTP set up)
FTP data connection set up with 22330
FTP data connection set up with 128.193.54.168
Data transfering...

client: listing file on128.193.54.168
 cct.txt
 a.out
 READ.ME
 lol.txt
 ftserver.c
 server
client: FTP control connection closed

RESULT 1: ==>server will show this: (not closed...)

FTP server open on port 22330

  FTP server connect with 128.193.54.168
  Receiving data port (FTP active mode) ...
  Receiving command ...
  Seting up data connection ...
  Server sending the listing..
  Data sesssion will be terminated...
Server: data connection completed!

STEP 3: ==>client: client directory will have a new file called lol.txt, it will have same content as in .py directory.
flip1 ~/cs372/prog2/client 1057$ ftclient.py flip1.engr.oregonstate.edu 22331 -g lol.txt 33220

Client: Control sesssion set up with 128.193.54.168 : 22330
Sending client port to server...(FTP set up)
FTP data connection set up with 22330
FTP data connection set up with 128.193.54.168
Data transfering...

Client: file transfer finished
client: FTP control connection closed


RESULT 2:==>server will show this: (not closed...)

FTP server open on port 22330

  FTP server connect with 128.193.54.168
  Receiving data port (FTP active mode) ...
  Receiving command ...
  Seting up data connection ...
  Sever sending file...
  Data sesssion will be terminated...
Server: data connection completed!

CONTINUE==>client: if you want keep testing go back to step 2 OR 3

FINISH==>server
^C



