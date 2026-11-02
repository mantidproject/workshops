# Mantid Developer Workshop 2014

*Migrated from the retired Mantid wiki page `Category:Workshop2014`. Hotel and travel logistics were not carried over.*

## When

20 Pre-workshop New developer masterclass (Will be held if there is enough interest)

21-24 January 2014 - Main Workshop

## Where

SNS, ORNL

Room C156, SNS Central Lab and Office Building.

## Agenda

## Monday - Pre-workshop New developer masterclass

Timings to be agreed by attendees

#### Topics

As directed by attendees, possibly including:

- Current development and testing practices (dos and do nots)
- Building mantid on your development machine
- Introduction to the Mantid codebase
- Instrument definition files
- Python scripting

## Tuesday

### Tuesday Morning

- 09:30 Start
- 10:30 Break
- 11:00 Resume
- 12:00 Lunch

#### Topics

- Introduction (Nick)
- C++ tips / best practice, including C++11 (Russell)
- Ways of working
   1. Coding Standards / static analysis (Martyn)
   2. Testing procedures (Owen)
   3. Task management (Nick)
      1. Ticket creation (Nick)
      2. Testability (Nick)
   4. Release Process (Nick)
   5. Documentation
      1. Current procedures Documentation / Wiki-maker (Owen)
      2. Bundled documentation: It's the future
      3. Python usage documentation (sphinx): Currently hard to use & scattered.
      4. Usage documentation: A user request. How to enforce and prevent rot.
- [Build servers - configuration and jobs](https://developer.mantidproject.org/JenkinsConfiguration.html) (Martyn/Stuart)
- [Git Workflow](https://developer.mantidproject.org/GitWorkflow.html) (Martyn)
   1. [The Macros](https://developer.mantidproject.org/GitWorkflow.html#Workflow_Git_Commands) (Martyn)
   2. Reverting a commit to develop (Martyn)
- Useful_Tools_for_Developers (Martyn)
- Discussion of areas where our processes might be refined
   - Please consider before hand what hinders you in your work.

### Tuesday Afternoon

- 13:30 Resume
- 15:00 Break
- 15:30 Resume
- 17:00 Adjourn - no organized dinner

#### Topics

- Live Data processing Rollout (Russell/Nick)
   - Next steps (Russell)
- How to write IDF files (Anders / Michael)
   1. Indirect Geometry Challenges - Discussion
   2. ISIS IDF-ISIS-SANS2D-annotated
   3. SNS [mantidgeometry repo](http://github.com/mantidproject/mantidgeometry)
   4. How to use the [schemas](https://docs.mantidproject.org/nightly/concepts/CreateanIDF.html) (Anders)
- Model optimization walkthrough and examples (Anders)
   1. Instrument parameters and curve fitting (Anders)
   2. Migrating values from GSAS/Fullprof (Anders)
   3. Writing new fitting functions (Martyn)

### Topics for Further Discussion

- Moving to Other issue tracking solutions
- Documentation Infrastructure

## Wednesday

### Wednesday Morning

- 09:00 Start
- 10:30 Break
- 11:00 Resume
- 12:00 Lunch

#### Topics

- Requirements from the SSC
   - [Overview](https://github.com/mantidproject/documents/blob/master/Presentations/Scientific Steering Committee/SSC 2014/SSC 2014 mantid plan.ppt?raw=true) - Nick
   - More detailed Notes - Scientific_Steering_Committee_2014
   - Split into groups Preliminary designs and initial estimates
   - Tools:
      - GUIs - [Balsamiq](http://builds.balsamiq.com/b/mockups-web-demo/)
      - Diagrams - [draw.io](http://www.draw.io/)
      - Estimates - [estimate spreadsheet](https://docs.google.com/spreadsheet/ccc?key=0Aq36k77Hr7BldGtZcnhxOG9NWjBYZTdTRVN6aGh3bGc&usp=sharing)

### Wednesday Afternoon

- 13:00 Resume
- 15:00 Break
- 15:30 Resume
- 17:30 Adjourn for dinner

#### Topics

- Requirements from the SSC - Continued
   - Presentation of preliminary designs
   - Group review
   - Refinement of estimates

## Thursday

### Thursday Morning

- 09:00 Start
- 10:30 Break
- 11:00 Resume
- 11:45 Photo
- 12:00 Lunch

#### Topics

- Mantid migration away from facility hosted infrastructure (Russell)
   - Moving to GitHub Issues.
   - Coherent Documentation infrastructure and markup
- New storage solution for system test data (Russell)
- Potential retirement of Managed Workspaces and long-term fate of 32-bit binaries (Russell)
- [Storing data in MD workspaces](https://github.com/mantidproject/documents/blob/464646dd65f14abbef5b6622f8088545deb17809/Presentations/DevMeetings/2014-01-22/MDworkspaces/MDWorkspaces-DevMeeting2014.pptx?raw=true) (Andrei)
- FORTRAN Algorithms ? (Jon)
- To be debated (Ricardo and any other volunteers) :
   - How to properly store scans within Mantid.
      - Is a scan to be treated as multi dimensional workspace?
      - Multiple variables varied during a scan: a complex scan may move in 4D QE space (e.g. triple axis instruments).
      - Examples of ScanningInstruments

### Thursday Afternoon

- 13:00 Resume
- 15:00 Break
- 15:30 Resume
- 17:00 Adjourn - no organized dinner

#### Topics

- Walkthrough of the DG Reduce GUI and scripts
   - Lessons Learned
   - Discusion of area of improvement
   - Discussion of future adoption as a common model
- Instrument View/Window - could/should it be more flexible (added by Russell)
- WorkspaceProperty & Workspace groups (Russell)

## Friday

### Friday Morning

- 9:00 - 12:00 Group Discussions on areas of interest
- 10:00 - 12:00 Mantid PMB (Nick, Jon, Garrett)
- 12:00 Lunch
