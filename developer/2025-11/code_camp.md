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
Info moved to https://github.com/mantidproject/mantid/issues/40277

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
- [FilterEvents](https://developer.mantidproject.org/Testing/Utility/FilterEventsInterfaceTest.html) - The non-GUI instructions are going to be unit tested, reducing the manual testing steps by half, the GUI needs a bit of refactoring before adding the unit tests.
- **ILL/Drill** interface does not have Manual Testing procedure, but already a system test which could be updated [here](https://github.com/mantidproject/mantid/blob/main/Testing/SystemTests/tests/framework/DrillProcessTest.py)
- **ILL/Simple Scan Viewer** (a derivative of the slice viewer) test could be created instead of creating a Manual Testing procedure


Tuesday activities
=================
CSNS Texture Pipeline
---------------------
Info moved to https://github.com/mantidproject/mantid/issues/40277


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

Update VSCode debugger configuration
------------------------------------
Got stuck on a silly oversight when setting up the VSCode debugger on Linux: the path to the executable program should be a full path and not contain '~', otherwise the executable is not found.
Update to the documantation: [Draft PR](https://github.com/mantidproject/mantid/pull/40274/files)

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

Wednesday activities
=================

CSNS Texture Pipeline
---------------------
Info at https://github.com/mantidproject/mantid/issues/40277

Fix Gaussian peak fitting
-------------------------
Continue with https://github.com/mantidproject/mantid/pull/40267
Down from 17 failed systems tests to 7 now we have altered the coordinate transform (rather than removing it)

This will be continuated after the meeting (check the PR for last updates)
