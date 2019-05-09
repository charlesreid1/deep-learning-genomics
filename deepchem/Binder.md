# Installing DeepChem on Binder

Instructions for installing DeepChem into a
binder on [mybinder](https://mybinder.org/).

This utilizes [ctb/deepchem-binder](https://github.com/ctb/deepchem-binder)
to create the binder image.

## Table of Contents

* [Start a DeepChem Binder](#start-a-deepchem-binder)
* [Install DeepChem into Binder](#install-deepchem-into-binder)

## Start a DeepChem Binder

Start a binder by visiting the URL: 
<https://mybinder.org/v2/gh/ctb/deepchem-binder/master>

This will take a few minutes to start a binder.
Once you see the Jupyter notebook file browser 
interface, click New > Terminal. This will open 
a new browser window with a terminal.

**NOTE:** The browser tab with the Jupyter 
notebook file browser interface may freeze up, 
which will leave you with only a command line
(no notebooks or plotting capability). _It is 
recommended that you start a new Jupyter Notebook
at this point._ You will need to restart the kernel 
of that notebook once the DeepChem installation steps
below are complete.

## Install DeepChem into Binder

In the tab with the terminal, issue the following command:

```
conda install -y -c deepchem -c rdkit -c conda-forge -c omnia deepchem==2.1.0
```

This will use the latest version of Python available
on binder.org (Python 3.6). It will take several minutes
to install everything.

Once everything has been installed, you can return
to the Jupyter notebook (or start a new notebook from
the file browser interface tab, if it is still alive).
Restart the notebook kernel so that it will have access
to DeepChem.

Verify that DeepChem is installed by executing the 
following in a notebook cell:

```
import deepchem as dc
```

If you need to verify the version of Python you are
using, execute the following in a notebook cell:

```
import sys
print(sys.executable)
```

