# Reduce Server Time in CI/CD

## The build time itself is not slow
The build often uses a "dirty" build, from a previous build on the runner, so the number of changed files is often minimal.
Looking at some PRs with a dirty build, the first test began running within 2 minutes.
It is therefore the *tests* that are taking up the majority of the time.

## Ways to reduce test time
We came up with several ideas to resduce the testing time
1. Since mantid version 6.4, only 553 of the approx 1000 algos have been used.  Deprecating/removing these would reduce the number of tests, hence testing time.
2. Mapping the dependencies would allow selectively running only those unit tests which depend on the changed code.
3. Many of the Qt interfaces for mantid reside in the mantid repo.  Moving these to separate repos with their own builds/tests could reduce strain on the mantid builds.
4. Configure multiple pushes to the same PR to build from the same runner, when possible.
5. Split the functionality into multiple domains (e.g. Powder Diffraction, Single Crystal, Single Crystal Inelastic, etc.), which are packaged into separate libraries that are optionally loaded by the users, each separatelt built and tested.
6. Make the unit tests and systems tests smaller.  Profiling tests, such as those testing time to process large data structures, could be broken off and run separately only occasionally.


# Concrete Ideas

## See how removing algos/tests impacts runtime

1. Identify the unused algos.
2. **In separate branch** comment these out from cmake lists (with their tests)
3. Measure how long tests run in branch (from start of tests to end of tests)
4. Uncomment these algos/tests, measure how long

Does removing the algos save us time?

## Identify performance tests

Go through tests, identify which are performance tests.

Comment these out (e.g. `test` --> `xtest`) and see how much time is saved.

If this significantly improves test times, consider moving performance tests to onyl build on nightly.

## Use dependency trees

Identify the file in Doxygen build which stores the dependency tree.

Experiment with ways to use this tree to inform the test suite.

There is a [script here](https://www.flourish.org/cinclude2dot/) which is capable of analyzing C++ codebases for #include directives and building dependency trees.  CTest has the ability to set "labels" on files, and [only run tests of certain labels using the `-L` directive](https://stackoverflow.com/questions/67865677/how-to-force-ctest-only-run-unit-tests-in-some-subdirectories).  A combintation of these, using the script to get dependencies, setting labels on the dependent files, then using `-L` in ctest to only run files with that label, could enable only running dependent tests.

This could speed up the tests run on the PRs, as only tests impacted by the changed files actually need to be checked.

## Split off systems tests

The linux runners finish running unit tests in about 15-20 minutes.  The remaining time is spent on the systems tests.  To give more rapid feedback to devs, reporting back if unit tests pass or fail on linux first, before running system tests, could speed up the dev cycle.  If the unit tests fail, the dev will more quickly know to fix something; if the unit tests pass, the dev may feel comfortable going ahead an marking a PR ready for review.

## Minimize systems tests

The linux runners finish running unit tests in about 15-20 minutes.  The remaining time is spent on the systems tests.  The SNSPowderRedux system test suite is a major offender, with multiple tests taking over 200s, several over 500s. Perhaps decreasing the size of the test data to these files will reduce the amount of time these tests spend running.   Below is a list of some of the slow systems tests
 - SNSPowderRedux
 - LoadLotsOfFiles
 - D7YIGPositionCalibrationTest
 - ILLPowderEfficiencyClosureTest
 - CorelliPowderCalibrationTest
 - ISIS_WISHPowderReductionTest
 - ISIS_PowderOsirisTest
 - ISIS_PowderPolarisTest
