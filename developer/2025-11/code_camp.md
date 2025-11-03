Ideas for code camp activities
==============================

Cross off items if they are rejected. 
Cross off and add link to new location if they are picked up.

- pixi https://github.com/mantidproject/mantid/pull/40190
- migrate to github-actions https://github.com/mantidproject/mantid/issues/39497
- qt5 -> qt6 planning and decisions https://github.com/mantidproject/mantid/issues/38415
- switch jemalloc to mimalloc and benchmark for memory and speed on linux and windows: https://github.com/mantidproject/mantid/issues/40249

Monday activities
=================

CSNS Texture Pipeline
---------------------

Initial testing of with an existing IDF that they have at CSNS and a cobbled together script for simulating groupings and an example table as if there was a set of fit parameters
```
# import mantid algorithms, numpy and matplotlib
from mantid.simpleapi import *
import matplotlib.pyplot as plt
import numpy as np
from Engineering.texture.TextureUtils import create_pf_loop

ws = LoadEmptyInstrument(Filename=r'C:\Users\kcd17618\Documents\MantidScripts\CSNS-texture\EMD_Definition_bank.xml', OutputWorkspace='empty-idf')
ax = ws.getAxis(0).setUnit("dSpacing")
Rebin(InputWorkspace=ws, OutputWorkspace=ws.name(), Params='0.9,0.005,1.1')
GenerateGroupingPowder(InputWorkspace='empty-idf', GroupingWorkspace='grp', AngleStep=2)
DiffractionFocussing(InputWorkspace='empty-idf', OutputWorkspace='empty-idf-foc', GroupingWorkspace='grp')

CreateEmptyTableWorkspace(OutputWorkspace='tab')
CreatePoleFigureTableWorkspace(InputWorkspace='empty-idf-foc', PeakParameterWorkspace='tab', OutputWorkspace='pf')


ws = mtd["empty-idf-foc"]

tab = CreateEmptyTableWorkspace('param')
tab.addColumn('double','I')
tab.addColumn('double','X0')
tab.addColumn('double','chi2')

for i in range(ws.getNumberHistograms()):
    tab.addRow((i,1.0,0.0))

exp_name = 'test'
save_root = r"C:\Users\kcd17618\Engineering_Mantid"

dir1 = np.array((0,1,0))
dir2 = np.array((1,0,0))
dir3 = np.array((0,0,1))

dir_names = ('d1','d2','d3')

kernel = 6.0
    
create_pf_loop(wss = ("empty-idf-foc",),
               param_wss = (["tab",],),
               include_scatt_power = False,
               scat_vol_pos = (0,0,0),
               readout_columns = "I", 
               dir1 = dir1, 
               dir2 = dir2, 
               dir3 = dir3, 
               dir_names = dir_names, 
               scatter = True,
               kernel = kernel, 
               save_root = save_root, 
               exp_name = exp_name, 
               projection_method = "Azimuthal")
```

<img width="887" height="741" alt="image" src="https://github.com/user-attachments/assets/965ba737-10fb-4475-b3e7-4a99a90701b3" />

TODO:

Make a better IDF with proper instrument hierarchy. Try and get this to work with real data or use this in another proof of concept script?


Fix cppcheck warnings
---------------------
* const reference and const pointer - Reece
* shadow variables - Marie
* cstyle casts - Andrei

Hot reloading algorithms
------------------------
