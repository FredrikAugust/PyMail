# PyMail
A simple command line based email client written in Python.

This new program is based on my old python email client which you can find here: https://github.com/Tijndagamer/Python_Email_Client

# Installation

First, clone the repo:

    git clone https://github.com/Tijndagamer/PyMail.git
    
Then make pymail executable:

    cd PyMail/src
    chmod +x pymail
    
Then you can move pymail to ~/bin/ so you can use it everywhere:

    mv pymail ~/bin/

If you still can't run pymail from other place than ~/bin, you have add this line to ~/.bashrc:

    echo export PATH=~/bin:"$PATH"
    
and then run this command:

     . .bashrc
    
If you don't want to re-enter your credentials every time you use PyMail you can run

     pymail config
     
This will store your credentials in a place where PyMail can find it, but please note that the files generated by config **are not encrypted or protected.** 

# Usage

#####Sending an email can be done in two ways.

The first way is to simply run this command:

    pymail send
    
After you hit enter, you wil be prompted to enter the email address of the receiver of the email, the subject of the email and the body of the email.

The second way is to this command:

    pymail send <receiver> <subject> <body>
    
This will immediately sent the email to receiver with subject as subject and body as body.
**Please note that any arguments given which should contain spaces, you have to put double quotes around them.

#####Receiving an email can also be done in two ways.

The first way is to simply run this command:

    pymail receive
    
This command will retrieve and print the latest email.

The second way is to run this command:

    pymail receive <n>
    
This will retrieve the nth email in your email. (-1 being the latest email you got)

**Tip:** If you receive an email full of HTML you can tunnel the output to a html file like this:

    pymail receive > email.html

You can also read an email you wrote using another text editor and send it using the file option:

    pymail file <filename> <delete_concept>

The layout of your file should be like this:

    to_address
    ---
    subject
    ---
    body


######Other options

If you're not sure what the options were again, run this:

    pymail help
    
This command wil print a short list of the possible options.

# Known issues

* When the subject is given from the command line it cannot have any spaces in it (this is fixed when you put it between quotes or double quotes)
* config / loading credentials only works when the user is in ~/bin
