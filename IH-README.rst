Ironhack Open edX Devstack
==========================

Get up and running quickly a development environment with Open edX services.

We'll set an environment variable with the name of the release of Open edX

.. code:: sh

    export OPENEDX_RELEASE=hawthorn.master


We need a python virtual environment to run our project inside it. We'll use `virtualenv`, a tool to create isolated Python environments. It creates a folder which contains all the necessary executables to use the packages that a Python project will need.

.. code:: sh

    pip install virtualenv                                     #install virtualenv tool

Create vitual python enviroment and activate it:

.. code:: sh

	mkdir ih-lms                                               #create project evironment folder
	cd ih-lms                                                  #move inside folder
	virtualenv pythonenv                                       #create virtual environment called pythonenv
	source pythonenv/bin/activate                              #activate virtual environment

Clone GitHub ironhack/ih-lms-devstack repo:

.. code:: sh

	git clone https://github.com/ironhack/ih-lms-devstack.git  #clone edx devstack repo
	cd ih-lms-devstack                                         #move inside repo

Initialize application:

.. code:: sh

	make requirements                                          #install requirements 
	make dev.clone                                             #clone edx repos
	make ih.dev.clone                                          #clone ironhack theme repo
	make pull                                                  #update docker images used by the application
	make dev.provision                                         #initialize application

Finally, launch application:

.. code:: sh

	make dev.up                                                #launch services and run application

To stop application:

.. code:: sh

	make stop
