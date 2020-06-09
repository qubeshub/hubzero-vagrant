QUBES Vagrant
===============
This is a Scotch Box vagrant setup for the QUBES instance of the HUBzero Content Management System. The main motivation is to create a portable and disposable environment for web development.

** This is NOT a production-ready system!! ** 
The passwords are weak, information may be included in the database, file permissions are not properly set, etc. etc. etc. Why? Because let the sysadmins worry about it while you write your code.
Please checkout [the official HUBzero Website](https://hubzero.org/download) for more secure options. 

If you have issues, [please create an issue on GitHub](https://github.com/hubzero/hubzero-vagrant/issues).

The original scotch-box documentation can be found here: [https://github.com/scotch-io/scotch-box/blob/master/README.md](https://github.com/scotch-io/scotch-box/blob/master/README.md). There are some useful things like MailCatcher which can help development.

## Installation and Setup
Make sure you have [Vagrant](https://www.vagrantup.com/downloads.html), [VirtualBox](https://www.virtualbox.org/wiki/Downloads), and [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) installed before proceeding to the next steps.

Once Vagrant and VirtualBox are installed, using a Terminal application:
- Run `git clone https://github.com/qubeshub/hubzero-vagrant`
- Within the newly created hubzero-vagrant directory, run `vagrant up`.
- Log into the machine at http://192.168.33.10 with the following credentials:
  - Username: `admin`
  - Password: `vagrant2016`

Two plugins need to be disabled on the vagrant box to work.  These plugins (`app/plugins/system/subnav` and `app/plugins/system/menurouter`) are important on production to route urls to the correct menu items.  They are not important, however, on the vagrant machine and will cause problems if left activated.

To deactivate these plugins, log into the administrative interface at http://192.168.33.10/administrator as `admin` (using the password above).  Once logged in, go to `Extensions -> Plug-in Manager`, search for `subnav` and/or `menurouter` in the search field, and click the green check icon under `STATUS` to deactivate the plugin.  Make sure you deactivate both on the vagrant machine.

## Notes
When the `vagrant up` script is run, it uses git, composer, and muse. The former two require an internet connection.

See the [Get Started](https://box.scotch.io/docs/) section of the Scotch Box documentation for more information on working with Vagrant, including how to access the server using ssh and where to find MySQL database credentials.