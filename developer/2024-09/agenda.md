**Location:** Science Building 213

Things discussed/decided
========================

- Forking Mantid
  - ORNL has a public fork that pushes to upstream
  - CSNS and ILL have private forks
  - ILL pushes to upstream periodically
- Modularisation Mantid
  - Breaking Mantid into smaller bits
  - Using Mantid as a library
  - What is the future of scientific interfaces and mantid modularization?
    - How would we break out interfaces so they can be discovered?
    - Questions about documentation
- wild/asterix imports
- pytest for unit tests
- Rewrite of instrument view
- The move to numpy v2

What has always bugged me about mantid is...
--------------------------------------------
- C++17/20
   - std::filesystems https://github.com/mantidproject/mantid/issues/37868
   - std::optional https://github.com/mantidproject/mantid/issues/37875
- Github Actions
- Build times
- Jenkins
- MVP (talk to Rob)
- Instrument View
- Coverity (needs RHEL9)
- Matplotlib
- Python typing
- rust
- Build tree
- External Interfaces
- External Data (segmentation)
- cxx testgen
  -google tests
- Randomised test order
- unstable tests
- long running tests
- cppcheck suppressions
- clang tidy
- Debugging QStrings
- Dependencies (Renovate/Dependabot)
- Standardisation
  - XML libraries (mxml, libxml, poco)
  - Geometry (opengl, stuart, opencascade)
  - nexus (nexusio, nexusfile, hdf5, nexus)
  - multithreading (documentation for standardisation)
  - python binding (boost vs pybind11)
  - guis in `scripts/`
  - algorithms in `scripts/`
  - instrument specific guis
- Mantid nightly
- loadeventnexus
- poco (logging, xml, net, multithreading)

CI Meeting
----------

- DevOps virtual team looks after the Mantid services including Error Reporter, Usage Reporter, Mailing Lists, Leeroy, Jenkins, Static website, Traeffic and Forum.
- DevOps team also looks after the runners at ISIS including for 4 Windows, 11 Linux and 4 Mac (2x x86 and 2x M1).

- Tom Hampson (ISIS Core team) will be looking at moving us away from Jenkins to GitHub Actions.
- Caila Finn (ISIS LSS team) will be working on a DevOps project during v6.12 to make the pipelines more stable. Three key focuses:
  - Dependency management (RenovateBot)
  - Connectivity (storing external data on a central node)
  - Better ways to run system tests (for example sometimes they pass on Linux, then fail the nightly on Mac).
- Randy (ORNL team) will be looking at improving the stability of their build servers. An easier build methodology.

- Special label for Coverity
- Access to job runner documentation
- Update linux docker images to RHEL9. Use conda linux anvil?

Things not covered, but suggested
---------------------------------
- Request from users on Debugging review with various IDEs
- What is a reasonable size for a PR? Is there a maximum size?


Agenda
======

Monday
------
* 09:00 Welcome and Announcements
* 09:15 Introductions
* 10:30 coffee
* 11:00 Round table - What has always bugged me about mantid is...
* 12:00 lunch (ESRF/ILL common restaurant)
* 13:00 Break into small groups
* 14:30 Review results of small groups
* 15:00 Break into small groups
  * CI and build servers (hybrid)
* 15:30 coffee
* 16:30 Summary from the day
* 17:00 Adjourn for dinner

Tuesday
-------
* 09:00 Convene
* 10:00 coffee
* 10:30 Summary from the meeting
* 11:00 Departure of ISIS colleagues
* 12:00 Adjourn for lunch
