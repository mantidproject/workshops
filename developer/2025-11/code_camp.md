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
* const reference and const pointer - Reece - https://github.com/mantidproject/mantid/pull/40261
* shadow variables - Marie - https://github.com/mantidproject/mantid/pull/40260
* cstyle casts - Andrei - https://github.com/mantidproject/mantid/pull/40259

Hot reloading algorithms
------------------------
[PR link for documentation on how to do this with existing mantid code.](https://github.com/mantidproject/mantid/pull/40258/)

LLM service integration into workbench
--------------------------------------
- Branch: https://github.com/mantidproject/mantid/compare/main...mantid_ai_service_impl
- LLM hosted on an interval server at STFC using llama.cpp.
- Model used: https://huggingface.co/Qwen/Qwen2.5-7B-Instruct-GGUF
- LLMService designed for users to be able to register their own LLMS, provided they have a REST API.
- Work done to give the LLM context (LLM is stateless, so we have to build conversation history in context).
- ADS content and AlgorithmManager registered algorithms added to contents (hitting issues due to length of prompt, we think - yet to be resolved)
- Index of vector DB created from the mantid documentation using FAISS (Facebook AI Similiarity search). This index can effectivelty be used to generated a dynamic, more focussed context to aid the prompt.

Work to do:
- Create middleware to run dynamic prompt creation (RAG workflow), and allow for further customisation in the future.
- Fix issues with prompt length


Investigate what manual tests could become unit tests
-----------------------------------------------------
Tests which have been investigated:
- [ALFView](https://developer.mantidproject.org/Testing/Direct/ALFViewTests.html) - Cannot be converted to unit tests: has too much GUI interaction.
- [DGSReduction](https://developer.mantidproject.org/Testing/Direct/DGSReductionTests.html) - Can be converted; mostly deals with TOFTOF. [Issue created #40263](https://github.com/mantidproject/mantid/issues/40263), no code/PR.
- [MSlice](https://developer.mantidproject.org/Testing/Direct/MSliceTestGuide.html) - Cannot be converted: too much GUI interaction.
- [SliceViewer](https://developer.mantidproject.org/Testing/SliceViewer/SliceViewer.html) - Some parts (checking what buttons/tabs enabled depending on input workspace) already have tests and can be removed; other parts too interactive and cannot be unit-tested.
- [Sample Transmission Calculator](https://developer.mantidproject.org/Testing/General/SampleTransmissionCalculatorTestGuide.html) - Could be converted to unit tests
- [FilterEvents](https://developer.mantidproject.org/Testing/Utility/FilterEventsInterfaceTest.html) - Parts could be unit tested (Adri working on this).


Tuesday activities
=================
CSNS Texture Pipeline
---------------------
Bit of a test IDF from modifying ENGINX
```
<?xml version="1.0" encoding="UTF-8" ?>
<!-- For help on the notation used to specify an Instrument Definition File
     see http://www.mantidproject.org/IDF -->
<instrument xmlns="http://www.mantidproject.org/IDF/1.0"
            xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
            xsi:schemaLocation="http://www.mantidproject.org/IDF/1.0 http://schema.mantidproject.org/IDF/1.0/IDFSchema.xsd"
 name="EMD" valid-from   ="1900-01-31 23:59:59"
                           valid-to     ="2100-01-31 23:59:59"
		           last-modified="2025-11-03 15:00:00">
<!-- Instrument description for EMD -->
<defaults>
  <length unit="meter" />
  <angle unit="degree" />
  <reference-frame>
    <along-beam axis="z" />
    <pointing-up axis="y" />
    <handedness val="right" />
  </reference-frame>
  <default-view view="spherical_y"/>
</defaults>

<!-- First, the source and sample -->

<component type="source">
  <location z="-49.5" />
</component>
<component type="sample position">
  <location />
</component>
<type name="source" is="Source">
  <properties />
</type>
<type name="sample position" is="SamplePos">
  <properties />
</type>



<component name="Bank1" type="detector-bank" idlist="Bank1">
  <location x="0" y="0" z="0" rot="90" axis-x="0" axis-y="1" axis-z="0"/>
</component>

<component name="Bank2" type="detector-bank" idlist="Bank2">
  <location x="0" y="0" z="0" rot="-90" axis-x="0" axis-y="1" axis-z="0">
    <rot val="180" axis-x="0" axis-y="0" axis-z="1" />
  </location>
</component>

<type name="detector-bank">
  <properties />
  <component type="detector-module">
    <location  x="0" y="0" z="0" rot="18.4" axis-x="1" axis-y="0" axis-z="0"/>
    <location  x="0" y="0" z="0" rot="12.26667" axis-x="1" axis-y="0" axis-z="0"/>
    <location  x="0" y="0" z="0" rot="6.133333" axis-x="1" axis-y="0" axis-z="0"/>
    <location  x="0" y="0" z="0" rot="0" axis-x="1" axis-y="0" axis-z="0"/>
    <location  x="0" y="0" z="0" rot="-6.133333" axis-x="1" axis-y="0" axis-z="0"/>
    <location  x="0" y="0" z="0" rot="-12.2666667" axis-x="1" axis-y="0" axis-z="0"/>
    <location  x="0" y="0" z="0" rot="-18.4" axis-x="1" axis-y="0" axis-z="0"/>
  </component>
</type>

<type name="detector-module">
  <component type="detector-block">
    <!-- Five of these -->
    <location  r="2" t="-10.82" p="0"> <facing x="0.0" y="0.0" z="0.0"/> </location>
    <location  r="2" t="-5.92" p="0"> <facing x="0.0" y="0.0" z="0.0"/> </location>
    <location  r="2" t="0.0" p="0"> <facing x="0.0" y="0.0" z="0.0"/> </location>
    <location  r="2" t="5.92" p="0"> <facing x="0.0" y="0.0" z="0.0"/> </location>
    <location  r="2" t="10.82" p="0"> <facing x="0.0" y="0.0" z="0.0"/> </location>
    <!-- One of these -->
  </component>
</type>

<type name="detector-block">
  <component type="detector-pixel">
    <locations y="-0.096" y-end="0.096" n-elements="64" name="pixel"/>
  </component>
</type>


<type name="detector-pixel" is="detector">
  <cuboid id="shape">
    <left-front-bottom-point x="-0.0015" y="-0.0015" z="0.0"/>
    <left-front-top-point    x="-0.0015" y=" 0.0015" z="0.0"/>
    <left-back-bottom-point  x="-0.0015" y="-0.0015" z="0.001"/>
    <right-front-bottom-point x=" 0.0015" y="-0.0015" z="0.0"/>
  </cuboid>
  <algebra val="shape"/>
</type>



<idlist idname="Bank1">
  <id start="100001" end="102240"/>
</idlist>

<idlist idname="Bank2">
  <id start="200001" end="202240"/>
</idlist>


</instrument>
```

Created a more comprehensive script with some trivial texture experiment

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


ws = mtd["empty-idf-foc"]
wss = ["empty-idf-foc"]
for i, ang in enumerate(np.linspace(-90,90, 20)):
    CloneWorkspace(InputWorkspace = ws, OutputWorkspace = f"ws{i}")
    SetGoniometer(ws, Axis0 = f"{ang}, 0, 0, 1, 1")
    wss.append(f"ws{i}")

tabs = []
for x, wsname in enumerate(wss):
    tab = CreateEmptyTableWorkspace(OutputWorkspace = f'param{x}')
    tab.addColumn('double','I')
    tab.addColumn('double','X0')
    tab.addColumn('double','chi2')
    for i in range(ws.getNumberHistograms()):
        val = 0 if i >= 8 else 1
        tab.addRow((val,1.0,0.0))
    tabs.append(f'param{x}')

## wss = list of workspace names where each one is a run with a goniometer set and a spectrum for each point in the pole figure
# tabs = list of tables where each table corresponds to one of the ws in wss and each row of the table is a fit for the peak of interest

exp_name = 'test'
save_root = r"C:\Users\kcd17618\Engineering_Mantid"

dir1 = np.array((0,1,0))
dir2 = np.array((1,0,0))
dir3 = np.array((0,0,1))

dir_names = ('d1','d2','d3')

kernel = 6.0
    
create_pf_loop(wss = wss,
               param_wss = (tabs,),
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
<img width="896" height="739" alt="image" src="https://github.com/user-attachments/assets/63e07780-b73a-4de4-8136-8187edd2f4bb" />


LLM service integration into workbench
--------------------------------------

Investigate what manual tests could become unit tests
-----------------------------------------------------

If a system test is modified, run it on all OS for that PR
----------------------------------------------------------
[Draft PR](https://github.com/mantidproject/mantid/pull/40265)

Fix Gaussian peak fitting
-------------------------

https://github.com/mantidproject/mantid/pull/40267
<img width="920" height="360" alt="image" src="https://github.com/user-attachments/assets/06f9da83-813c-4cb2-82cd-64d06909bd5e" />

Coverity
--------
[Draft PR](https://github.com/mantidproject/mantid/pull/40266)

Cppcheck fixes
--------------
Marie and Reece

Faster builds
-------------
* skip doxygen when no cpp files are modified https://github.com/mantidproject/mantid/pull/40270
* running cmake instrumentation on 4.2rc2 to collect trace metrics that may point to painpoints in the build.  Hopefully eventually generate a flamegraph.
