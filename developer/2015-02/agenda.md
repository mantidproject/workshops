# Mantid Developer Workshop 2015

*Migrated from the retired Mantid wiki page `Category:Workshop2015`. Hotel and travel logistics were not carried over.*

## Monday 2nd February

### Monday Morning CR16/17, R80

- 09:30 Start
- 10:30 Coffee Break
- 12:00 Group Photo
- 12:10 Lunch

#### Topics

- Welcome & Introduction (Nick)
- Ways of working (Nick)
   - [Communication](https://developer.mantidproject.org/Communication.html)
   - Task management (Nick)
      1. Ticket creation
         - Core Tickets
      2. [Ticket workflow](http://trac.mantidproject.org/mantid/wiki)
      3. Changes with pull request
      4. The future of Tickets and migration plans
      5. Testability (exampes [[1]](http://trac.mantidproject.org/mantid/ticket/10959), [[2]](http://trac.mantidproject.org/mantid/ticket/7523), [[3]](http://trac.mantidproject.org/mantid/ticket/9843), [[4]](http://trac.mantidproject.org/mantid/ticket/6338), [[5]](http://trac.mantidproject.org/mantid/ticket/10894),[[6]](http://trac.mantidproject.org/mantid/ticket/10917) )
- Git/github tutorial (Pete)
   - [Pull Requests](http://github.com/SpinWaveGenie/SpinWaveGenie)
   - Issues
- [Coding Standards](https://developer.mantidproject.org/Standards/index.html) (Anders)
- Testing procedures (Owen)
   1. [Future Plans](https://github.com/mantidproject/documents/blob/master/Project-Management/TechnicalSteeringCommittee/meetings/TSC-meeting-2015-Pull-Request-Plan.md)
   2. [unit tests](https://developer.mantidproject.org/UnitTestGoodPractice.html)
   3. mocking
   4. [MantidPlot tests](https://github.com/mantidproject/mantid/tree/master/Code/Mantid/MantidPlot/test)
- Documentation (Martyn)
   - [Overview](https://raw.githubusercontent.com/mantidproject/documents/master/Design/Documentation/Documentation new workflow.png)
   - http://www.mantidproject.org/Category:Development - Developer pages
   - http://www.mantidproject.org - Wiki
   - [http://docs.mantidproject.org/](http://docs.mantidproject.org/) - Statically generated user documentation
   - [Documentation Guide For Devs](https://developer.mantidproject.org/Standards/DocumentationGuideForDevs.html) - Guildines for documenting algorithms/concepts/Python in .rst.
- [Build servers - configuration and jobs](http://builds.mantidproject.org/) (Martyn)
   - Static Analysis (Pete)

### Monday Afternoon CR16/17, R80

- 13: 00 Resume
- 15:30 Coffee Break
- 17:00 Adjourn

#### Topics

- UB matrices in Mantid (Andrei)
- [Crystallographic support in Mantid](http://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2015-02-02/Mantid-Crystallography-MW.pdf) (Michael Wedel)
- Managing (testing) data files with CMake (Martyn)
   - [Data Files in Mantid](https://developer.mantidproject.org/DataFilesForTesting.html)
   - [Repository layout](https://github.com/mantidproject/mantid/tree/feature/10869_external_data_support/Code/Mantid/Testing/Data)

## Tuesday 3rd February

### Tuesday Morning CR03, R68

- 09:00 Start
- 10:30 Coffee Break
- 12:00 Lunch

#### Topics

- Design Patterns In Mantid (Martyn)
- [Guidelines on writing a good design document](https://developer.mantidproject.org/DesignDocumentGuides.html) (Owen)
   1. [Example of options](https://github.com/mantidproject/documents/blob/master/Design/EmbeddedInstrumentInfoNexus.md)
   2. [Example of questions](https://github.com/mantidproject/documents/blob/master/Design/IntegratingAdept.md)
   3. [Example of design](https://github.com/mantidproject/documents/blob/master/Design/Live_Event_Data_Detailed_Design_Document.doc)
- Plans from new facilities using Mantid and group discussions about best way to tackle issues
   - Presentation from CSNS, ILL, ESS, PSI, Juelich, Andrei (TAS) (10 mins each)
   - Design possible approaches in groups (1 hr)
   - Present designs to all (10 mins each)

### Tuesday Afternoon CR03, R68

- 13:00 Resume
- 15:30 Coffee Break
- 17:00 Adjourn

#### Topics

- Correct practices for parallelisation (Steven)
- Central services people should be using - a non-exhaustive list (Pete)
   - [Algorithm::validateInputs](http://github.com/mantidproject/mantid/blob/master/Code/Mantid/Framework/API/src/Algorithm.cpp#L291) (SetSampleMaterial [1](http://github.com/mantidproject/mantid/blob/master/Code/Mantid/Framework/DataHandling/src/SetSampleMaterial.cpp#L133) and [2](http://github.com/mantidproject/mantid/blob/master/Code/Mantid/Framework/DataHandling/src/SetSampleMaterial.cpp#L77))
   - File operations + cross-platform paths with Poco
   - Mutex
   - Boost::regex NOT poco - Anything from header only and only regex, python, date_time
   - [Run](http://docs.mantidproject.org/nightly/api/python/mantid/api/Run.html) [ExperimentInfo::mutableRun()](http://github.com/mantidproject/mantid/blob/master/Code/Mantid/Framework/API/inc/MantidAPI/ExperimentInfo.h#L102) and [Sample](http://docs.mantidproject.org/nightly/api/python/mantid/api/Sample.html) [ExperimentInfo::mutableSample()](http://github.com/mantidproject/mantid/blob/master/Code/Mantid/Framework/API/inc/MantidAPI/ExperimentInfo.h#L97)
   - PropertyManager ([cpp](http://github.com/mantidproject/mantid/blob/master/Code/Mantid/Framework/Kernel/inc/MantidKernel/PropertyManager.h) and [python](http://docs.mantidproject.org/nightly/api/python/mantid/kernel/PropertyManager.html))
   - [Finding an IDF path](https://docs.mantidproject.org/nightly/concepts/InstrumentDefinitionFile.html#IDF_filename_convention)
- Python Scripting (Martyn)
   - Exposing To Python
      - [Example of exporting Run object](https://github.com/mantidproject/mantid/blob/master/Code/Mantid/Framework/PythonInterface/mantid/api/src/Exports/Run.cpp)
   - Debugging best practices (Martyn)
- Lightning talks from SSC meeting (5 mins per area, secretary from each group)
- Instrument Geometry (Anders)
   - [Instrument Definition File](http://docs.mantidproject.org/nightly/concepts/InstrumentDefinitionFile.html)
   - [Moving parts](http://docs.mantidproject.org/nightly/concepts/InstrumentDefinitionFile.html#using-parameter)
   - [Mantid geometry repository](http://github.com/mantidproject/mantidgeometry)

### Tuesday Evening

## Wednesday 4th February

### Wednesday Morning CR16/17, R80

- 09:00 Start
- 10:30 Coffee Break
- 12:00 Lunch

#### Topics

- [MD workspace Nomalisation](https://github.com/mantidproject/documents/blob/a9ff38fce35e9cc5657709c33db24f06cd36edb7/Presentations/MD-ORNL-seminar.pptx?raw=true) (Andrei)
   - Also invite scientists
- Fitting (Roman)
   - Basic capability
   - Multi data fitting
   - Fitting from script
   - [Using fitting inside an algorithm](https://github.com/mantidproject/mantid/blob/master/Code/Mantid/Framework/Algorithms/src/FitPeak.cpp#L642)
   - Using Fitting inside another user interface
   - 2D and more exotic fitting
- Writing and modifying fit functions (Anders)
   - [In the Mantid Framework](https://github.com/mantidproject/mantid/tree/master/Code/Mantid/Framework)
   - Extending Mantid
   - Modifying parameters of existing fit functions
- Modifying Algorithms: Do's and Don'ts (Martyn)
- C++ tips / best practice, including C++11 (Martyn)

### Wednesday Afternoon CR16/17, R80

- 13:00 Resume
- 15:30 Coffee Break
- 17:00 Adjourn

#### Topics

- Overview of the Workspace Types (Owen)
   1. what is in the workspace Workspace
   2. Types of workspaces [MatrixWorkspace](https://docs.mantidproject.org/nightly/concepts/MatrixWorkspace.html) [MDWorkspace](https://docs.mantidproject.org/nightly/concepts/MDWorkspace.html)
      1. data [ISpectrum](https://github.com/mantidproject/mantid/blob/master/Code/Mantid/Framework/API/inc/MantidAPI/ISpectrum.h) [historam data](https://github.com/mantidproject/mantid/blob/master/Code/Mantid/Framework/DataObjects/inc/MantidDataObjects/Histogram1D.h) [event data](https://github.com/mantidproject/mantid/blob/master/Code/Mantid/Framework/DataObjects/inc/MantidDataObjects/EventList.h)
      2. run object
      3. Instrument
      4. WS Parameter Map and what it does
- Overview of MD Visualization (Owen)
   1. SliceViewer overview
      1. Python Interface examples
      2. LineViewer
      3. PeaksViewer
   2. Vates Simple Interface
      1. Current state
      2. What's coming next
- Event filtering (Pete)
- [Workflow Algorithms](https://docs.mantidproject.org/nightly/concepts/WorkflowAlgorithm.html) (Stuart)
   1. What is so special about them
   2. Controlling logging and understanding history
   3. Extra things you need to do
