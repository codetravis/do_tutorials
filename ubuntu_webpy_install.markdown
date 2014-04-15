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

More advanced users may wish to install web.py from source.  To do this you need to first download the web.py source.

<pre>
wget http://webpy.org/static/web.py-0.37.tar.gz
</pre>

The next step is to extract the files using the tar utility to make it usable.

<pre>
tar -xvfz web.py-0.37.tar.gz
</pre>

Once this is done, you have two options:
1. Move or copy the "web" folder into your project directory.
<pre>
cp web /path/to/project/.
</pre>
2. Make web.py accessible to all applications.
<pre>
cd web
sudo python setup.py install
</pre>


