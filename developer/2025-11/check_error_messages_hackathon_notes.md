# Check your error messages Hackathon

- Statements which assert that an exception is thrown, but don't check the error message, can hide bugs.
- `self.assertRaises` -> `self.assertRaisesRegex`

```python
self.assertRaisesRegex(
    RuntimeError,
    "Maximum simulated X value is lower than maximum reference X value",
    NMoldyn4Interpolation,
    InputWorkspace=sim,
    ReferenceWorkspace=self.osiris,
    OutputWorkspace="__NMoldyn4Interpolation_test",
)
```

```python
with self.assertRaisesRegex(ValueError, "algorithm name"):
    parent_alg.createChildAlgorithm(startProgress=0.0, endProgress=1.0, enableLogging=False, version=1, **{"XUnit": "Wavelength"})
```

- `TS_ASSERT_THROWS` -> `TS_ASSERT_THROWS_EQUALS`

```c++
TS_ASSERT_THROWS_EQUALS(model.setFunctionString("name=LinearBackground,A0=1,A1=2"), const std::runtime_error &e, std::string(e.what()), "Model doesn't contain a convolution.");
```

## Structure

- Find instances of `assertRaises` and `TS_ASSERT_THROWS`
- Group into sets of ~N instances (whole number of files)

## Mechanics

- Hosted on github using a project
  - Column limits on the project to enforce only so many 'sets' being 'active'
- Can work individually or in teams
- Base number of points for completing a set
- Bonus points for finding a bug hidden by bad tests
- Bonus points for adding a new test
- Multiplied by teams bonus
- Points for reviewing / merging PRs

## Do's / Don'ts

### Do

- Think carefully about changes
- Add tests for any untested throw / raise statements you find
- Raise issues when you discover a false positive if it is complex
- Fix false positive tests when it is simple

### Don't

- Add in the error message without checking it makes sense in the context
- Feel pressured to rush a complex fix, just raise an issue

