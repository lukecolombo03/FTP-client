# Project 2 Networks & Distributed Systems, January 2023
## Description
This project is to implement File Transfer Protocol (FTP) in a client that runs on the command line. 
This client can perform operations like list, make directory, remove, remove directory, copy, and move.

## Approach
My program starts by parsing the command-line arguments to get the username, password, host, port,
and path from the ftp url. It then connects the control channel to the server, and has short if
else statements for mkdir, rmdir, and rm (which don't require the data channel at all). If the
operation does require the data channel, it goes to another function, which sets up the data channel
and executes copy, move, or list. I combined copy and move into one helper function because the 
code was so similar.

I followed the implementation steps that were written out in the assignment description. It took 
quite a bit of time to parse the arguments with the correct syntax because I was not familiar with
the argparse module, and was a little confused by the command line arguments for this project. 
I implemented the command channel and was able to log in pretty easily, and tested my code by 
printing out whatever the socket received from the server. This also helped me do PASV and set up 
the data channel. I ran into a lot of issues with uploading/downloading files to and from the server,
and this took a lot of debugging by printing out variables and error messages. I first tested everything
with my own files uploading to the provided ftp server, and then by submitting to gradescope because
there were still some minor errors.
