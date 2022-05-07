Installation
============

AstroScheduller Python Package
------------------------------

Prerequisites
~~~~~~~~~~~~~

There are several python packages are required to run the
AstroScheduller are listed below. All those packages are included in a
standard Anaconda environment.

-  numpy
-  matplotlib
-  requests

The ``Astropy`` Package is not required by the AstroScheduller. However,
it is highly recommended, since several AstroScheduller functions are
compatible with Astropy objects (such as coordinates and time objects).

Using setup.py
~~~~~~~~~~~~~~

**Since the preview version of the AstroScheduller Package is not yet
published into the PyPi, ``setup.py`` can be used to install the
package.**

Firstly clone the project from the Github before installing
AstroScheduller with the setup.py:

.. code:: shell

   git clone https://github.com/AstroScheduller/AstroScheduller.git

Switch to the ``AstroScheduller`` directory:

.. code:: shell

   cd ./AstroScheduller

Run the installation:

.. code:: shell

   python setup.py install

Once the installation process is completed, you may test the package by
the following commands to see if it works:

.. code:: shell

   (base) wenky@Wenkys-MacBook-Pro GitHub % python
   Python 3.x.xx
   Type "help", "copyright", "credits" or "license" for more information.
   >>> import astroscheduller
   >>>

So far you have finished with the Python part of the installation; the
GoLang part of the AstroScheduller (called the ``AstroSchedullerGo``) is
not usually included in the Python package. The pre-build version of the
AstroSchedullerGo Module is automatically downloaded from Github as the
package has been imported if the internet is connected as well as **a
pre-built version for the platform is available**.

If errors such as *“The pre-build version of the AstroScheduller Module
is not available”* and *“OSError: /xxx/xxx.so: invalid ELF header”* is
reported, it means there is no pre-build module available for your
platform. In this case, please see Install the AstroSchedullerGo Modules
for more information.

AstroSchedullerGo Modules
-------------------------

There are several pre-built versions of AstroSchedullerGo are provided,
even though they are not guaranteed to perfectly work on all the devices
and platforms.

To check if a pre-build version of the module is available for your
platform, use the following Python scripts:

.. code:: python

   import astroscheduller as ash
   ash.core().update()

The AstroSchedullerGo Module will be downloaded if a pre-build version
is found; otherwise, an exception *“The pre-build version of the
AstroScheduller Module is not available”* will be reported.

What if there is no pre-build version available for my platform?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If you are unfortunately not to be provided with a pre-build version,
you may need to compile the source code yourself. The compilation
process will be easy if you already have a GoLang environment on your
device.

By using the following command to build the module:

.. code:: shell

   cd /PATH/TO/ASTROSCHEDULLER/ && go build -buildmode=c-shared -o _scheduller.so ./*.go

Then, use the