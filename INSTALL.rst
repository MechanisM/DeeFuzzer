# -*- coding: utf-8 -*-
#
# Copyright (c) 2007-2010 Guillaume Pellerin <pellerin@parisson.com>
# All rights reserved.
#
# This software is licensed as described in the file COPYING, which
# you should have received as part of this distribution. The terms
# are also available at http://svn.parisson.org/deefuzzer/DeeFuzzLicense.
#
# Author: Guillaume Pellerin <pellerin@parisson.com>


Dependencies
=============

depends:  python, python-dev, python-xml, python-shout | shout-python, libshout3,
	  libshout3-dev, python-mutagen

provides: shout-python | python-shout, python-tinyurl

optional: python-twitter, python-liblo | pyliblo (>= 0.26)

recommends: icecast2, python-setuptools, stream-m


Install
=========

Please first install libshout3 and liblo from source OR libshout3-dev and liblo-dev from your own distribution package manager.

Now, the easiest way to install the DeeFuzzer from a shell::

	sudo pip install deefuzzer

or::

	sudo easy_install install deefuzzer

To install the DeeFuzzer from sources, go to the main deefuzzer app directory, for example::

    cd deefuzzer-0.5.0

and run::

    sudo python setup.py install

For more informations, see http://svn.parisson.org/deefuzzer/


Twitter (manual and optional)
================================

To get track twitting, please install python-twitter, python-oauth2 and all their dependencies.

Install python-oauth2::

    sudo easy_install oauth2

Get and install python-twitter (>= 0.8.1)::

    wget http://python-twitter.googlecode.com/files/python-twitter-0.8.1.tar.gz
    tar xzf python-twitter-0.8.1.tar.gz
    cd python-twitter-0.8.1
    sudo python setup.py install

As Twitter access requires oauth keys since 07/2010, you need to get your own access token key pair.
Please run the dedicated script to do this from the main deefuzzer app directory::

    python tools/get_access_token.py

You will be invited to copy/paste an URL in your browser to get a pin code.
Then copy/paste this code into the console and press ENTER.
The script gives you a pair of keys : one access token key and one access token secret key.

Change the <twitter> block options in your deefuzzer XML config file, giving the 2 keys.
For example::

    <twitter>
            <mode>1</mode>
            <key>85039615-H6yAtXXCx7NobF5W40FV0c8epGZsQGkE7MG6XRjD2</key>
            <secret>A1YW3llB9H9qVbjH8zOQTOkMlhVqh2a7LnA9Lt0b6Gc</secret>
            <tags>Music Groove</tags>
    </twitter>

Your DeeFuzzer will now tweet the currently playing track and new tracks on your profile.


OSC Control
=============

Working, but no doc yet. Please read the code :)

