# How to Install Web.py on Your Ubuntu VPS

## Introduction

When it comes to Python, there is no shortage of web frameworks to choose from. Web.py is a small python web framework created by Aaron Swartz and is designed to allow you to be able to truly let you write web apps in Python.  It can be very rewarding to work with and is fairly easy to install.

The following set of instructions were performed on an Ubuntu 12.04 VPS.

## Prerequisites

The only prerequisite you need is python and that should come pre-installed on your server. To find out which version of Python you have type:
<pre>
python --version
</pre>

It should output:
<pre>
python 2.7.4
</pre>

Or something similar.


## Install Web.py Using Pip

Using Pip, installing web.py is fairly straightforward. But first you need to sintall pip. In Ubuntu, this is easily done using the package manager.
<pre>
sudo apt-get install python-pip
</pre>

Once that is finished, simply use pip to install web.py.
<pre>
sudo pip install web.py
</pre>

## Install Web.py from Source

An alternate method that more advanced users may wish to use is to install web.py from source.  To do this you need to first download the web.py source.
<pre>
wget http://webpy.org/static/web.py-0.37.tar.gz
</pre>

The next step is to extract the files using the tar utility to make it usable.
<pre>
tar -xvfz web.py-0.37.tar.gz
</pre>

This should give you a folder named web.

Once this is done, you have two options:
1. Move or copy the "web" folder into your project directory to make it accessible to just that project.
<pre>
cp web /path/to/project/.
</pre>

2. Or make web.py accessible to all applications.
<pre>
cd web
sudo python setup.py install
</pre>


## Testing the Installation

Web.py comes with a builtin development server.  To test the install, in your project directory create a python file (name is not important, but for this example it is named "code.py") with the following contents:
<pre>
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
</pre>

Now, assuming you named your file "code.py", from the command line type:
<pre>
python code.py
</pre>

You should then see the following output:
<pre>
http://0.0.0.0:8080/
</pre>

Now if you visit your server by typing its IP address (let's say it is 23.45.67.89) followed by the port number 8080 into the address bar of your web browser,
<pre>
http://23.45.67.89:8080/
</pre>

you should see "Hello, world!" in your browser.
