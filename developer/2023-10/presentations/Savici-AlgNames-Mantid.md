# Naming algorithms

---

# 1. Conventions

* Names no longer than 20 characters https://github.com/mantidproject/mantid/blob/main/Testing/SystemTests/tests/framework/CodeConventions.py
* No underscores or spaces, only letters and numbers
* Start each word with a capital letter
* Numbers are allowed, after first character 
* "If possible, avoid abbreviations unless they are common and well understood."
* Standard prefixes for common tasks: 
  
  - ~~ http://www.mantidproject.org/Mantid_Standards#Naming ~~
  - https://developer.mantidproject.org/Standards/MantidStandards.html#naming

---

# 2. Inconsistent capitalization and abbreviations

* ~~ REFLReprocess and RefLReduction ~~
* TOFSANSResolution, ConvertEmptyToTof, EQSANSMonitorTOF, EQSANSTofStructure
* DNSFlippingRatioCorr, DetectorEfficiencyCor, CylinderPaalmanPingsCorrection
* AsymmetryCalc, SpecularReflectionCalculateTheta
* ConvertDiffCal, ConvertToDiffractionMDWorkspace

---

# 3. Incomplete names

* Technique specific algorithms:

  - ~~ CalculateResolution (Reflectometry only) ~~ NRCalculateSlitResolution (NR not Reflectometry)
  - ComputeSensitivity, IQTransform, Q1D (SANS)
  - RemoveLowResTOF (Powder Diffraction)
  - ModeratorTzero (Indirect)

--

* Cannot tell if some algorithms just generate some correction or apply it

  - AnnularRingAbsorption
  - AnvredCorrection
  - ModeratorTzero

---

# 4. Going into extreme - nonsensical names - does much more than the title impplies, or completely unexpected things

* What does MolDyn do?
* ~~ QLines, Quest ~~
* ResNorm
* TimeSlice

---

# 5. Inconsistent use of the same word

* What does Calculate... do?
  - CalculateEfficiency returns a workspace with efficiency
  - CalculateFlatBackground (by default) subtracts a constant
  - ~~ CalculateGammaBackground ~~ VesuvioCalculateGammaBackground does both

---

# 6. Multiple word choices to indicate the same action

* Load/ Import (2)
* Get (10)/ Calculate (31)/ Find (23)
* Create (30)/ Generate (9)/ Fake (3)/ Predict (5)
