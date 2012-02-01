ABOUT
-----

A no-facebook-please web app to run locally.
It erases any "Connect" / "I like" / other FB button from the websites you browse,
saving you some of bandwidth, concentration & time.


PREREQUISITES
-------------

* You have the right to do anything you want on you machine & in your LAN
* You have the right to resolve any domain name locally on you machine
* You have the right to modify locally the way websites you visit are rendered
* If these prereq can't be honored, avoid install this: Mark Z. may pay hundred of lawyers to sue you.
* This is a damn small quick'n dirty web-based app, to be run *locally* with Apache2 / IIS / WA(MP) server


INSTALL
-------

* copy this project in your /var/www folder
* Apache2 users : add this line to your /etc/apache2/apache2.conf :

    Include /var/www/pleasenofacebook.com/conf/apache2.conf

* check your Apache2 conf :

    apache2ctl -t

* reload Apache2 conf :

    sudo service apache2 reload


UNIT TESTS
----------

Just visit any website of the Internet. It surely has a "I like" button somewhere.
Well, it *had*, because you just changed this.


ANALYTICS & ROI
---------------

Some weeks after you installed this, have a look at your web server custom log file (see conf/apache2.conf).
Stunning, isn't it ?

Use `analog` for a fine-grained analysis:

    sudo apt-get install analog lynx
    analog +g/var/log/apache2/access.pleasenofb.log -O/tmp/analog.html
    lynx [ or firefox/chromium-browser] /tmp/analog.html


ROLLBACK
--------

Temporary : comment the line you added to your web server conf. By example for Apache2 :

    #Include /var/www/pleasenofacebook.com/conf/apache2.conf

Then reload Apache2 (see above)

Uninstall : remove all files or modification listed above, restart your web server. FB is back. Everywhere.


LICENSE
-------

* see LICENSE file


SUPPORT
-------

Ronan GUILLOUX, ronan.guilloux@gmail.com

