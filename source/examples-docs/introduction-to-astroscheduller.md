# Introduction to AstroScheduller

```python
# Example: Introduction to AstroScheduller
# https://github.com/xiawenke/AstroScheduller/blob/Dev/examples/intro_to_ash.py

import astroscheduller as ash                                # Import AstroScheduller

# Prepare for an example
ash.example("https://raw.githubusercontent.com/AstroScheduller/AstroScheduller/Dev/tests/psr_list_debug.xml")

obsPlan = ash.scheduller()                                   # Create a new scheduller object
obsPlan.objects.from_xml("./example.xml")                    # Load the objects from a XML file
obsPlan.get_schedule()                                       # Generate the schedule
obsPlan.stats()                                              # Calculate the statistics
obsPlan.plot().show()                                        # Plot the schedule
obsPlan.schedule.to_table("./example.txt")                   # Export the schedule to a table
```

    ========== STATS ==========
    | All Objects: 85
    | Scheduled Objects: 42
    | Unscheduled Objects: 43
    | Observation Duration: 83230
    | Wait Duration: 2820
    | Schedule Rate: 49.41%
    ===========================




![png](introduction-to-astroscheduller_files/AstroSchedullerGo_demo_0_1.png)


------------------------------------
Download/Open this example as: 
 - [script (*.py)](https://github.com/AstroScheduller/astroscheduller.github.io/blob/main/source/examples-docs/introduction-to-astroscheduller_files/intro_to_ash.py)
 - [notebook (*.ipynb)](https://github.com/AstroScheduller/astroscheduller.github.io/blob/main/source/examples-docs/introduction-to-astroscheduller_files/intro_to_ash.ipynb)
 - [Google Colab (*.ipynb)](https://colab.research.google.com/drive/1pnGP9p53ELxzyRdV7aMAa21Q0RGHIbaM?usp=sharing#scrollTo=sRRghTNwipp4)