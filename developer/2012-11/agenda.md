# Mantid Developer Workshop 2012

*Migrated from the retired Mantid wiki page `Category:Workshop2012`. Hotel and travel logistics were not carried over.*

## When

6-9 November 2012

## Where

R78 meeting room, Building R78, Rutherford Appleton Laboratory, UK

## Agenda

### Tuesday Morning

- 09:30 Start
- 10:30 Break
- 11:00 Resume
- 12:00 Lunch

#### Topics

- Introduction (Nick)
- C++ tips / best practice, including C++11 (Russell)
- GUI Overview (Martyn / Russell / Mathieu)
- Instrument display walkthrough (Roman)
- Custom algorithm dialogs (Martyn)
- Qt Widget development (Martyn)

### Tuesday Afternoon

- 13:30 Resume
- 15:00 Break
- 15:30 Resume
- 17:00 Adjourn for dinner

#### Topics

- Ways of working
   1. Coding Standards / static analysis (Martyn)
   2. Documentation / Wiki-maker (Owen)
   3. Task management (Nick)
      1. Ticket creation (Nick)
      2. Testability (Nick)
      3. Ticket rot (e.g. 3-year old tickets, 131 tickets assigned to 'Anyone'). What should we do about it? (Nick)
   4. Testing procedures (Owen)
   5. Release Process (Nick)
- OS & IDE options and survey (Martyn)
- [Build servers - configuration and jobs](https://developer.mantidproject.org/JenkinsConfiguration.html) (Martyn/Stuart)
- Working with Git (Russell)
   1. Different interfaces (Russell)
   2. Common workflow (Russell)
   3. How to do .. (Russell)
- Useful_Tools_for_Developers (Martyn)

### Wednesday Morning

- 09:00 Start
- 10:30 Break
- 11:00 Resume
- 12:00 Lunch

#### Topics

- Testing
   1. Unit test best practice / TDD (Owen)
   2. [System test best practice](https://developer.mantidproject.org/SystemTests.html) (Owen)
      1. Location for large system test data files (Russell)
   3. [Performance test best practice](https://developer.mantidproject.org/WritingPerformanceTests.html) (Owen)
   4. Unscripted Testing (Nick)
   5. Cross-checking output of interfaces vs their scripts (Martyn)
- Learning from our failures (Nick)
- Walkthrough of the Python Interface (Martyn)
- Automated data analysis & integration with meta data repositories
   1. ISIS (Anders) Workshop2012_ISIS_express_service
   2. SNS (Mathieu)

### Wednesday Afternoon

- 13:00 Resume
- 15:00 Break
- 15:30 Resume
- 17:00 Adjourn for dinner

#### Topics

- Model optimization walkthrough and examples (Roman)
   1. curve fitting (Roman)
   2. fitting table data sources (Roman)
   3. Model fitting of multiple datasets (Roman)
   4. Resolution convolution model fitting (Martyn)
- Interfacing with Third party modelling (Martyn)
- Live Data processing walkthrough (Russell)
   1. Next steps (Russell)
- How to write IDF files (Anders / Michael)
   1. ISIS Workshop2012_IDF_ISIS
   2. SNS [mantidgeometry repo](http://github.com/mantidproject/mantidgeometry)
- How to check IDF Files (Owen)

### Thursday Morning

(CNMS L183 Booked 8:30-13:00)

- 09:00 Start
- 10:30 Break
- 11:00 Resume
- 12:00 Lunch

#### Topics

- Tidy up topics
   1. Long build/Slow unit tests - A no change build takes ~10 mins on ISIS RHEL6, ~5mins is tests. (Martyn)
   2. SpectraDetectorMap vs ISpectrum (Martyn)
   3. Dead/Long unused algorithms (Martyn)
   4. Multiple NeXus APIs -> One (Martyn)
   5. *"Too many knobs?"* : Over time, certain classes/features in Mantid have garnered more and more options, which can make it difficult for developers to know how to use them and keep things consistent. A prime example seems to be sub-algorithms (store in ADS or not, history or not, logging or not,...). WorkspaceProperty is another candidate. What could/should we do to improve things? (Russell)
   6. History and C++ Workflow Algorithms : C++ workflow algorithm use is calling for more complex history creation/tracking than is currently available. (Russell - item suggested by Michael)

- ISIS long term plan (Nick)
   1. Multiple scattering corrections (Nick)
   2. Client server Mantid (Nick)
   3. Web / Cloud interfaces (Nick)
   4. Designing for the user - Keeping it simple (Nick)
   5. Instrument control from Mantid (Nick)

### Thursday Afternoon

- 13:00 Resume
- 15:00 Break
- 15:30 Resume
- 17:00 Adjourn for dinner

#### Topics

- VATES progress & capabilities (Owen)
   1. next steps (Nick)
   2. VSI, is it necessary? (Owen)
   3. Working with MD data 101 (Owen)
- Distributed analysis / HPC
   1. Approaches (Ross)
   2. Chunking (Ross)
   3. ORNL facilities and implementation (Ross)
   4. ISIS facilities and implmentation (??)
- Units & subunits (Nick)
- Masking past, present and future. (Nick)

### Friday Morning

- 9:00 - 12:00 Group Discussions on areas of interest
- 12:00 Lunch

### Friday Afternoon

- 13:00 Resume
- 15:30 Resume
- 17:00 Adjourn for dinner
