# How to Install Web.py on Your Ubuntu VPS

## Introduction

When it comes to Python, there is no shortage of web frameworks to choose from. Web.py is a small python web framework created by Aaron Swartz and is designed to allow you to be able to truly let you write web apps in Python.  It can be very rewarding to work with and is fairly easy to install.

The following set of instructions were performed on an Ubuntu 12.04 VPS.

## Prerequisites

The only prerequisite you need is python and that should come pre-installed on your server. To find out which version of Python you have type:
~~~~
python --version
~~~~

It should output:
~~~~
python 2.7.4
~~~~

Or something similar.


## Install Web.py Using Pip

Using Pip, installing web.py is fairly straightforward. But first you need to sintall pip. In Ubuntu, this is easily done using the package manager.
~~~~
sudo apt-get install python-pip
~~~~

Once that is finished, simply use pip to install web.py.
~~~~
sudo pip install web.py
~~~~

## Install Web.py from Source

An alternate method that more advanced users may wish to use is to install web.py from source.  To do this you need to first download the web.py source.
~~~~
wget http://webpy.org/static/web.py-0.37.tar.gz
~~~~

The next step is to extract the files using the tar utility to make it usable.
~~~~
tar -xvfz web.py-0.37.tar.gz
~~~~

This should give you a folder named web.

Once this is done, you have two options:
1. Move or copy the "web" folder into your project directory to make it accessible to just that project.
~~~~
cp web /path/to/project/.
~~~~

2. Or make web.py accessible to all applications.
~~~~
cd web
sudo python setup.py install
~~~~


## Testing the Installation

Web.py comes with a builtin development server.  To test the install, in your project directory create a python file (name is not important, but for this example it is named "code.py") with the following contents:
~~~~
import web

urls = (
    '/', 'index'
)

class index:
    def GET(self):
        return "Hello, world!"

if __name__ == "__main__":
    app = web.application(urls, globals())
    app.run()
~~~~

Now, assuming you named your file "code.py", from the command line type:
~~~~
python code.py
~~~~

You should then see the following output:
~~~~
http://0.0.0.0:8080/
~~~~

Now if you visit your server by typing its IP address (let's say it is 23.45.67.89) followed by the port number 8080 into the address bar of your web browser,
~~~~
http://23.45.67.89:8080/
~~~~

you should see "Hello, world!" in your browser.
