# 01.Getting Started: Installation

## Installation

#### Prerequisites

There are several python packages are required to run the AstroScheduller are listed below. All those packages are included in a standard Anaconda environment. 

 - numpy
 - matplotlib
 - requests

The `Astropy` Package is not required by the AstroScheduller. However, it is highly recommended, since several AstroScheduller functions are compatible with Astropy objects (such as coordinates and time objects). 

#### Using PyPI

The most recent stable version of  AstroScheduller Package is available on PyPI. Using the following command to install the package and the required packages will automatically be installed: 

```bash
pip install AstroScheduller
```

If you already have an older version of AstroScheduller installed, as AstroScheduller is currently in active update, we strongly recommend that you often update the package as follows

```{shell}]
pip install --upgrade astroscheduller
```

The AstroScheduller GUI uses a package called [Tkinter](https://tkdocs.com/tutorial/install.html), which is required since AstroScheduller v1.0.0. **This package will not be able to install automatically by PyPI. **If you are using the [Anaconda](https://www.anaconda.com), the Tkinter Package might be included in the distribution. To check if Tkinter has been already installed, try the following: 

```{shell}
Python 3.8.10 | packaged by conda-forge 
Type "help", "copyright", "credits" or "license" for more information.
>>> import tkinter
```

If Tkinter is not installed, an exception will be thrown. Then, **the Tkinter installation would be as the following**: 

```{shell}
# For Ubuntu: 
sudo apt-get update && sudo apt-get install python3-tk

# For MacOS: 
## You should first install the Homebrew software, then install the Tkinter. 
## Using the command as follows: 
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" && brew install python-tk
```

The Tkinter installation methods that were mentioned above are the fastest way of doing that. Please see [Tkinter website](https://tkdocs.com/tutorial/install.html) for more information. 



## Plan for the First Observation with AstroScheduller

Congratulations, you have now completed all the installation, and are ready to plan for yourself. First observation with AstroScheduller. There is a quick example that demonstrates how the package works:

```python
import astroscheduller as ash                                # Import AstroScheduller

# Prepare for an example
ash.example("https://raw.githubusercontent.com/xiawenke/AstroScheduller/Dev/tests/psr_list_debug.xml")

obsPlan = ash.scheduller()                                   # Create a new scheduller object
obsPlan.objects.from_xml("./example.xml")                    # Load the objects from a XML file
obsPlan.get_schedule()                                       # Generate the schedule
obsPlan.stats()                                              # Calculate the statistics
obsPlan.plot().show()                                        # Plot the schedule
obsPlan.schedule.to_table("./example.txt")                   # Export the schedule to a table
```

In this example, a pre-prepared XML format file is read and automatically planned. In the end, the planning results are presented in three different formats: some stats, a plot, and a table. 

In addition to importing XML format files, AstroScheduller also supports some more flexible ways of importing objects to be observed -- it's much more powerful than this simple demonstration. To go further, please see other examples or later chapters. 

## Troubleshooting

If reports such as *"The pre-build version of the AstroScheduller Module is not available "* and *"OSError: /xxx/xxx.so: invalid ELF header "* appear, this means that there is no pre-built [AstroScheduller Go Module](./build-from-source.html#astroschedullergo-modules) available for your platform. Since the core part of the AstroScheduller package is developed in Go, even though the project provides several pre-built versions of the modules to support most platforms, there are still some platforms that are not provided with pre-built versions of the modules.

In this case, you will need to build and install the module yourself. You can use the [installation script](./build-from-source.html#installation-install-sh) or follow the instruction about [how to build the module manually](./build-from-source.html#astroschedullergo-modules)  for instructions. If you think this is an error, rather than the platform being incompatible with pre-built modules, feel free to create an issue on [issues](https://github.com/AstroScheduller/AstroScheduller/issues). 
