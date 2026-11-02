# Tuesday small groups

*Migrated from the retired Mantid wiki page `DevWorkshop2016_Tue_small_group`.*

Notes from the Tuesday small groups discussions

## Algorithms

## Geometry

## Complex Code

Within the group we used SourceMonitor to assess the most compex code in Framework, using the Max Complexity, or branch counting approach described in clean code.

We reviewed the two most complex classes, one was a low level code in the heart of geometry for calculating bounding boxes. The other was an workflow algorithm with a complex and long exec function.

We found that in both cases there were relatively simple areas that could be refactored by extracting methods to class methods or otherwise. Some things you need to consider:

- Name extracted methods well
- Your refactoring should improve code readability, don't make the code harder to understand to please a metric.
- You don't need to be the author to refactor the code
- Ensure you have sufficient test coverage before you start refactoring.

## Crystallography

Framework/Crystal Technical Debt & QA

- String properties for point and space groups and reflection conditions
- V3D for HKL (define integer structure where needed)
- Developers not around (Janik Zikovsky, Dennis & Ruth Mikkelson)
- Complicated algorithms (9 constructors for Peak, hundreds of lines in exec e.g. IndexPeaks)
- Lack of tests (Some just test if algorithm executes, need system tests for long execs)
- Duplicate algorithms between ISIS & SNS (e.g. IndexPeaks and IndexSXPeaks)
- Some algorithms only need instrument or sample, but require MatrixWorkspace (write free function to get instrument from any type workspace)
- Should instrument and sample be in workspace?
- Should each peak have instrument when only sample orientation changes?
- Reduction workflow for single crystal is not documented (Don’t know what algorithms to use)
- Need equations used in algorithms documented (e.g. FindPeaksMD)
- Auto reduction difficult (possible if UB known?)
- Inconsistency using IPeak/Peak and IPeaksWorkspace/PeaksWorkspace in algorithms
- Some TOF algorithms do not work for HFIR
- Separate cases for RectangularDetector and tubes (Particularly WISH with 2 rows of tubes)
- GetComponentByName expensive and needed in many Crystal routines
- Usage of legacy software (e.g. ISAW for centering crystal and calibrating detectors)

## Properties

### Problem Algorithms

Briefly looking at how existing algorithms used complex properties, we discovered the following problem areas.

- Examples of algorithms badly using strings MDAlgorithms: **QLab**, **Dimensions** comma separated **Dimensions**, **MDFrame**, **Units**
- Algorithms taking a collection of Workspaces by string **MergeRuns**, **Stitch1DMany**

### Properties we could do with

Briefly looking at gaps in the property type system

- Vector of files
- Vector of workspaces
- Enum Property, not a string property with a StringListValidator
- Based on examples above, **Dimension**, `MDFrame` etc.

### How hard is it to add a new property?

How can we extend the PropertyTypes?

- Adding a new Property subtype is very hard, too many assumptions about **PropertyWithValue**. See dynamic casts in areas like **IPropertyManager**
- Adding **PropertyWithValue** is possible. See **OptionalBoolean** as a recent example at the time of writing.
- Adding a Vector WorkspaceProperty or Vector FileProperty would be a significant amount of work. Not clear the best route for this. The **WorkspaceProperty** has to be defined in API, and is significantly different from the Kernel PropertyWithValue&lt;T> types. This will be the next thing to figure out.
