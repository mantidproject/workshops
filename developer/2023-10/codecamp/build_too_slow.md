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
