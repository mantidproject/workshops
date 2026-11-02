# Mantid Developer Workshop 2016

*Migrated from the retired Mantid wiki page `Category:Workshop2016`. Hotel and travel logistics were not carried over.*

**NOTE: All information below is tentative and requires agreement from the various partner facilities.**

## When

- Jan 20-21 Scientific Steering Committee
- Jan 22 Project Management Board
- Jan 22 Technical Steering Committee
- Jan 25 Developer Design Meeting (open, but intended for partner facility members)
- Jan 26-28 Developer Workshop

## Where

[Central Laboratory and Office building of the Spallation Neutron Source](https://www.ornl.gov/sites/default/files/05-01786-outsideMC-.pdf) at Oak Ridge National Laboratory

## Agenda

### Scientific Steering Committee

Agenda

### Project Management Board

Room: C502

Time: 9:30 AM, Jan 22nd, 2016

### Technical Steering Committee

[Minutes](http://github.com/mantidproject/documents/blob/master/Project-Management/TechnicalSteeringCommittee/meetings/2016/TSC-meeting-2016-01-22.md)

**Morning** 09:00 C152

- Review of outstanding items discussed at previous [in-person meeting](https://github.com/mantidproject/documents/blob/master/Project-Management/TechnicalSteeringCommittee/meetings/2015/TSC-meeting-2015-01-29.md) & [fortnightly meetings](https://github.com/mantidproject/documents/blob/master/Project-Management/TechnicalSteeringCommittee/meetings/TSC-meeting-next.md)
- Review of requirements from IDF v2 - Campbell
- Review of requirements from Geometry v2 in-memory representation - Arnold
- Work breakdown for Geometry - Arnold
- Estimation and milestone map for Geometry requirements if possible - Arnold
- Whiteboard session sketching out design for IDF v2 & in-memory representation

**Lunch** 12:00 C152

- Roundtable: Continue design ideas sessions

**Afternoon** 13:00 C152

- Improving the current Units system - Peterson
- Shortlist items for 'Technical Debt' based on Simon's document - Heybrock

17:00 Adjourn

### Developer Design Meeting

C152

Jan 25 - Monday

09:00 **Morning**

- Current code-base structure: - Gigg
   - Good parts about current structure
   - Problems with current structure

- Future structure: - Gigg
   - What do we want to aim for?
   - Considerations:
      - Do we still want a plugin mechanism?
      - Better support for builds for server/headless environments
      - How should Python be integrated? (currently unavailable from the C++ layers)

12:00 **Lunch**

- Brief review of structures of other large open-source code bases ([paraview](http://github.com/kitware/paraview) and [matplotlib](http://github.com/matplotlib/matplotlib))

13:00 **Afternoon**

- Whiteboard session for sketching out aims. To include:
   - Python script structure
   - Packaging

17:00 adjourn

### Developer Workshop

CLO Rm C156

##### Jan 26 - Tuesday

09:00 **Morning**

- Welcome by senior ORNL manager
- Partner facility priorities
   - Presentation of SSC/PMB results by Draper
   - ORNL priorities by Granroth
   - ISIS priorities by Draper
   - ESS priorities by Taylor
   - [TSC report](http://github.com/mantidproject/documents/blob/master/Project-Management/TechnicalSteeringCommittee/reports/TSC-PMB-report-2016-01-22.md) and [workflow change](http://github.com/mantidproject/documents/blob/master/Project-Management/TechnicalSteeringCommittee/meetings/2016/TSC-meeting-2016-01-22.md) by Peterson
   - [Instrument 2.0](http://github.com/mantidproject/documents/tree/master/Design/Instrument-2.0) by Arnold
   - Code restructure by Gigg

12:00 **Lunch**

- Notable changes in mantid since the last developer meeting

13:00 **Afternoon**

- Lightning talks - session 1
- [Developer documentation debt](https://github.com/mantidproject/documents/blob/master/Project-Management/TechnicalSteeringCommittee/reports/GuidelinesAndStandards.md) by Markvardsen
- [Technical debt and QA](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2016-01/mantid-technical-debt.pdf) in Mantid by Heybrock
- Small group discussion by Peterson

##### Jan 27 - Wednesday

09:00 **Morning**

- [Software Engineering Best Practices](http://ricleal.github.io/Presentations/bestpractices.html) by Leal
- [Developer survey](https://github.com/mantidproject/documents/blob/master/Project-Management/TechnicalSteeringCommittee/reports/DeveloperSurveyResults2015.md) ([raw results](https://www.surveymonkey.com/results/SM-N5VB8VDJ/))
- Discussion

12:00 **Lunch**

- Published science that cites mantid - Granroth

13:00 **Afternoon**

- Lightning talks - session 2
- MPI and Mantid
   - Demo: "[Live data prototype](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2016-01/ess-live-data-prototype.pdf)" (ESS, early state) [ **Simon, maybe 15 min** ] (*slides partially broken in github preview, please download*)
      - study possibilities and problems of event mode
      - investigate new architecture: front end + Mantid MPI back end
   - Discussion & questions [ **30 min?** ]
   - [Introduction to MPI](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2016-01/mpi-introduction.pdf), so anyone interested can join/understand the rest of the session [ **Simon, 15 min** ]
   - Overview of existing MPI implementation in Mantid [ **Vickie, 15 min** ]
   - [Proposal for "new" MPI design](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2016-01/mantid-mpi-new.pdf) [ **Simon, 20 min** ] (*slides partially broken in github preview, please download*)
- Group photo at 15:00

16:00 HFIR Tour

18:30 Dinner at  ([menu](http://www.longhornsteakhouse.com/menu-listing/dinner))

##### Jan 28 - Thursday

09:00 **Morning**

- Presentation of developer survey discussion results
- Split into two parallel groups
   - Group 1:
      - Crystallography in Mantid, Michael Wedel
      - Instrument Control, IBEX, Michael Hart
   - Group 2:
      - MPI Discussion
- Lightning talks - session 3

12:00 **Lunch**

- Coding workflow ([fork](https://help.github.com/articles/fork-a-repo) and pull request) discussion - Whitfield

13:00 **Afternoon**

- Discussion of the 5-year plan ([ORNL plan](https://github.com/mantidproject/documents/blob/master/Design/ORNL_Mantid_5yearplan.pdf))
- notes
- [Information on priorities from the Developer meeting for the PMB](https://github.com/mantidproject/documents/blob/master/Project-Management/TechnicalSteeringCommittee/reports/DevMeetingItems-2016.md)

16:00 SNS Tour

17:00 Adjourn

##### Lightning Talk Topics

For those attending the workshop, please register any topics you'd like to briefly talk about. Deadline is 1st January for registering talks o the table, powerpoint presentations should be sent soon after. **A MAXIMUM of 5 minutes** is allowed for each talk, but less would be better. We encourage you to keep talks constructive, and use fresh materials rather than re-hash known issues.

Once we know how many talks we have, we'll split them out into slots. Things you should consider when preparing your talks:

- Talks will run back to back, so all slides must be handed-over well in advance of each session so that they can be co-located
- There will be no time for questions either during or after each talk. We should have break-out opportunities for further discussions
- If your talk exceeds 5 minutes you will be politely moved on to make way for the next person

| Title | Presenter | Session |
| --- | --- | --- |
| [Lessons from DDD](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2016-01/DDD/Domain_Driven_Development.pdf) | Owen Arnold | 1 |
| [DynamicFactory Pitfalls](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2016-01/DynamicFactory/Dynamic_Factory_Pitfalls.pdf) | Owen Arnold | 2 |
| [UI Usability and Reliability](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2016-01/UseabilityReliability/ui_useability_and_reliability.pdf) | Owen Arnold | 3 |
| [Python Packages: Worth looking into...](http://ricleal.github.io/Presentations/markdown/PythonStandards/presentation.html#/) | Ricardo Leal | 2 |
| [C++11: Making your code simpler since...](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2016-01/c++11-making-your-code-simpler-since-2011/slides.pdf) | Simon Heybrock | 1 |
| [Fitting: tests for accuracy and reliability](https://gnab.github.io/remark/remarkise?url=https%3A%2F%2Fraw.githubusercontent.com%2Fmantidproject%2Fdocuments%2Fmaster%2FPresentations%2FDevMeetings%2F2016-01%2Ffitting_tests%2Ffitting_tests2.md#1) | Fede M Pouzols (Anders Markvardsen) | 1 |
| [Using the C++ standard library with lambdas](https://gnab.github.io/remark/remarkise?url=https%3A%2F%2Fraw.githubusercontent.com%2Fmantidproject%2Fdocuments%2Fmaster%2FPresentations%2FDevMeetings%2F2016-01%2FLambdaExpressions%2Flambda.md) | Michael Wedel | 1 |
| [Symbol visibility 101](http://gnab.github.io/remark/remarkise?url=https%3A%2F%2Fraw.githubusercontent.com%2Fmantidproject%2Fdocuments%2Fmaster%2FPresentations%2FDevMeetings%2F2016-01%2FSymbols_Gigg%2FSymbols_Gigg.md) | Martyn Gigg | 2 |
| [Naming algorithms](https://gnab.github.io/remark/remarkise?url=https%3A%2F%2Fraw.githubusercontent.com%2Fmantidproject%2Fdocuments%2Fmaster%2FPresentations%2FDevMeetings%2F2016-01%2FAlgorithmNames_Savici%2FAlgNames_Savici.md) | Andrei Savici | 2 |
| [Organizing algorithms and documentation](https://gnab.github.io/remark/remarkise?url=https%3A%2F%2Fraw.githubusercontent.com%2Fmantidproject%2Fdocuments%2Fmaster%2FPresentations%2FDevMeetings%2F2016-01%2FDocumentation_Savici%2FDocumentation_Savici.md) | Andrei Savici | 3 |
| [Struggling with pylint and PEP 8](https://gnab.github.io/remark/remarkise?url=https%3A%2F%2Fraw.githubusercontent.com%2Fmantidproject%2Fdocuments%2Fmaster%2FPresentations%2FDevMeetings%2F2016-01%2Fpylint_pep8%2Fpylint_pep8.md#1) ([directory](https://github.com/mantidproject/documents/tree/master/Presentations/DevMeetings/2016-01/pylint_pep8)) | Fede M Pouzols | 2 |
| [Move Semantics: Some things to keep in mind](https://github.com/mantidproject/documents/blob/master/Presentations/DevMeetings/2016-01/MoveSemanticsCaveats/Some things to consider when using move semantics.pdf) ([directory](https://github.com/mantidproject/documents/tree/master/Presentations/DevMeetings/2016-01/MoveSemanticsCaveats)) | Anton Piccardo-Selg | 1 |
| [DataProcessorAlgorithms: Getting things for "cheap"](https://gnab.github.io/remark/remarkise?url=https%3A%2F%2Fraw.githubusercontent.com%2Fmantidproject%2Fdocuments%2Fmaster%2FPresentations%2FDevMeetings%2F2016-01%2Fdata_processor.md) | Pete Peterson | 2 |
| [MVP pattern in Mantid](https://github.com/mantidproject/documents/raw/master/Presentations/DevMeetings/2016-01/MVP_pattern/MVP.pdf) | Raquel Alvarez | 3 |
