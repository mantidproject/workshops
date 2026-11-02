# Mantid Developer Workshop 2018

*Migrated from the retired Mantid wiki page `Category:Developer_Workshop_2018`. Hotel and travel logistics were not carried over.*

## Where

SNS CLO room C156. Oak Ridge National Laboratory, Oak Ridge, TN ,USA

## Organising Committee

Mantid Technical Steering Committee

### Code Camp Ideas

- Fill in details for constant wavelength instruments
   - Workspace types
- Investigate how to share PyCharm projects across developers (+ other editors)
   - Investigate how to configure other IDE for users
- Investigate google benchmark
- See if we can build on [clcache](https://github.com/frerich/clcache) work for Windows builds
- Investigate the `pybind11` as a replacement for boost python. In particular what would buffer protocol support mean for us?
- Git hooks for checking clang-format on changeset and generate patch locally - should it be automatically applied?
   - If we dump the current LLVM config does it give a more consistent result across versions
- Restarting builds that have failed - unreliable tests
- Better handling for builds that hang
- Discussion for creating an overall plan for documentation
- Mantid property file gripes
   - Interpreting Mantid.user.properties is everywhere
   - Mantid overwrites user properties automatically
- Constant wavelength
- Total scattering

### Wednesday

09:00 **Morning**

- Welcome - Richard Ibberson
- Welcome - Nick Draper
- New Workbench
   - Developer details/experience tutorial - Martyn Gigg
   - [plotting](http://docs.mantidproject.org/nightly/api/python/mantid/plots/index.html) - Andrei Savici

10:30: **Tea/Coffee**

- Code camp planning
- Code camp (small groups):
   - Leeroy/Jenkins - automatically kill jobs in queue when another comes in for same PR (Ross)
   - Automating the process of checking the performance jobs (Lamar)
   - Discuss ideas for capturing run-time issues with Mantid (Keith/Matthew) - [https://github.com/mantidproject/documents/blob/21557_Error-reporting-framework-design/Design/CrashReporting/DesignDocument.md](https://github.com/mantidproject/documents/blob/21557_Error-reporting-framework-design/Design/CrashReporting/DesignDocument.md) design document)
   - [Investigate integration with Google test](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2018-01/google-test.md) (Simon + Dan)
   - [Standardize macOS developer setup](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2018-01/osx_breakout.md) (Gagik)

12:00 **Lunch**

- Reports from code camps
- ["This has always bugged me in mantid"](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2018-01/this_bugs_me_session.md) - Samuel Jackson

13:00 **Afternoon**

- Discussion: Mantid as a scipy styled library - Garrett Granroth
   - What does this mean?
   - How should the code be broken up to present a layered approach
   - Types of interaction (workbench/gui, jupyter notebooks/hub, ipython)
   - What libraries/packages do we interoperate with well (numpy, ipython, matplotlib, pandas?, xarray?, scipy.optimize?, lmfit?)

15:45 **Tea/Coffee**

16:00 **Tour of SNS**

17:00: **End**

### Thursday

08:00 Mantid 5km

09:00 **Morning**

- Instrument 2.0 update - Lamar Moore
   - [Instrument 2.0 Slides](https://github.com/DMSC-Instrument-Data/documents/blob/master/presentations/Instrument_2_0/Instrument 2.0 Update.pdf)
- MPI Updates - Simon Heybrock
   - [MPI introduction slides](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2016-01/mpi-introduction.pdf) from 2016 developer meeting.
   - [MPI support in Mantid slides](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2016-01/mantid-mpi-new.pdf) from 2016 developer meeting (marginally outdated but mostly correct).
   - [MPI support in Mantid slides](https://github.com/mantidproject/documents/blob/master/Presentations/Scientific Steering Committee/SSC 2018/mantid-user-2018-mpi.pdf) from 2018 user meeting.
   - [MPI documentation](http://docs.mantidproject.org/nightly/development/AlgorithmMPISupport.html).

10:30: **Tea/Coffee**

- [Interactive Matplotlib tutorial](https://github.com/AndreiSavici/InteractiveMatplotlib) - Andrei / Jose

12:00 **Lunch**

- Code camp planning

13:00 **Afternoon**

- Code camp (small groups)
   - Gallery of plots for using Mantid workspaces with matplotlib.
   - Absorption and Multiple Scattering discussion
   - Developer documentation rethink (reducing diversity, reducing markup languages, linking to/from external projects, ...)
      - setup second sphinx project for developer docs. Maybe `mantid/docs/user` & `mantid/docs/dev` directories?
   - On visual studio debug build, dealing with QString etc. can be difficult
- Reports from code camps

- Introduction to reactor/constant wavelength - Andrei Savici
   - Scanning instruments - Ian Bush
   - MD workspaces - Andrei Savici/Marina Ganeva

15:30: **Tea/Coffee**

17:00 **End**

18:00 **Workshop dinner** (No host)

- [Bonefish Grill](https://www.bonefishgrill.com/locations/tn/turkey-creek?utm_source=yext&medium=referral&utm_campaign=location_listings)
### Friday

09:00 **Morning**

- Junghoon Chae / Dynamic Color Mapping with a Multi-Scale Histogram
- Lightning talks (5 minutes)
   - New [workspace factory](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2018-01/workspace-factory.pdf) functions - Simon Heybrock
   - [Histogram Iterators](http://slides.com/samueljackson-1/histogram-iterators#/) - Samuel Jackson
   - Autoreduction at the ILL - Gagik Vardanyan
   - [Scripting Paraview](https://corelli.pages.ornl.gov/paraview) - Ross Whitfield
   - Eigen library - Antti Soininen
   - boost::python tutorial - Pete Peterson
      - [exposing new method on existing object](https://github.com/mantidproject/mantid/compare/tutorial_boostpy_method)
      - [an ugly example](https://github.com/mantidproject/mantid/pull/21322/files)
- [MVP](https://developer.mantidproject.org/MVPTutorial/index.html) in python + practical - Anthony Lim
- Crowdsourced talks
   - [Sharing git alias/cheat sheet](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2018-01/git_cheat_sheet.md)
   - [Tools that people use](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2018-01/dev_tools.md)
   - [Performance optimization --- Tales from the trenches](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2018-01/optimization_in_practice.md)

10:30: **Tea/Coffee**

- Code camp planning
- Code camp/discussions (small groups)

- User documentation
   - Standardize algorithm categories and fix them
   - Standardize references and generate a list of them
   - Top-level page for index of all categories
- SliceViewer/SpectrumViewer in new workbench
- Scanning instrument
- Adding static analysis for python (customize flake8)
- Build speed scripts. [Recent results](https://docs.google.com/spreadsheets/d/1XQSEY69SxH1JR604PvbKq9HEIIPe6Aa5vg8r_oeL5kU/edit#gid=1973794371) and [PR for the tools](https://github.com/mantidproject/mantid/pull/21683).

12:00 **Lunch**

- Reports from code camps

13:00 **Afternoon**

- Technique break-out / parallel sessions
- Custom interfaces (mslice, addie, ...)

15:00: **Tea/Coffee**

15:30 **Tour of HFIR**

17:00: **Adjourn**

## Place to put presentations

Presentations can be stored here [[1]](https://github.com/mantidproject/documents/tree/master/Presentations/DevMeetings/2018-01)
