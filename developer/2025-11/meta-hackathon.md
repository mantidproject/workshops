# Meta-Hackathon Notes, Results, and Feedback

## 🥇 Turbo Test
- Many unit tests take minutes rather than seconds to run.
- Aim to bring down this total runtime.
- Tests can be easily split. Teams decide which they look at.
- Running over subsets of data, blocking, efficient test setup.
- Points scored based on the absolute time saved. 
- Ensure test coverage is not diminished
- 10x bonus points for underlying code which is improved.

Final Score: 10

Trophies: 🏆 **Most Productive**, :trophy: **Most Collaborative**

## 🥈 M.A.R.G.A.R.I.T.A Party
- Lots of sub-packages of mantid
- Break up those packages into smaller to reduce interdependency
- Determine actual mantid interdependency trees
- Break mantid into those smaller packaged.
- Setup tests to only run those based on down-stream dependencies.
- Create new test data dependencies. Fewer data dependencies.
- Would need to be coordinated well.
- Once dependency tree exists, splitting into separate areas becomes more easy

Final Score: 9

Trophies: :trophy: **Most Unique**, :trophy: **Most Fun**

## 🥉 Check the Error Messages
- Large number of statements that don't use `self.assertRaisesRegex` or `TS_ASSERT_THROWS_EQUALS`.
	- Can easily hide bugs.
- Would be grouped into sets of files containing these missing test checks. Grouped by a whole number of files.
- Hosted on github using a project.
- Column limits in a project to enforce only so many sets being active.
- Can work individually or in teams.
- Base number for completing a set.
	- Bonuses: fixing bugs, new tests, team bonus
- Points for merging and reviewing. 
- Would need to enforce thinking carefully about changes.
	- Adding new tests for anything missing.
	- Raise issues for complex false-positives.
	- Fixing simple false-positives.
- Probably about a day's worth of work.

Final Score: 8

Trophies: :trophy: **Most Accessible**

## Improving Code Editor
- Code editor is well-compartmentalised, so given a general area to work on.
- One day
- Teams would come up with a list of ideas.
- Scoring: Usability, Performance, Code Quality, Test Coverage, Sustainability.

Final Score: 2

Trophies: :trophy: **Most Unique**

## Data Reduction
- Lots of large data files that users don't need access to.
- What are the largest files that are used.
- Only small portions of those are actually required.
- Should be possible to replace these with cropped versions with fewer rows and columns.
- Small memory fingerprint, easier to share with other developers and users.
- Creating a list of the files used in unit and system testing.
- Order the files from largest to smallest.
- Assign work between 5 teams based on the usage of those files.
- Would require a careful review. Benchmark tests would need to be updated. Need to ensure they're still representative of what they're testing. 
- Points based on: file size reduction, runtime reduction, PR reviews. How well-formed the PR is.

Final Score: 2

## Sustainability
- Reduce power consumption for processing
- Unit/System tests that run for too long
- Teams decide on an area they wish to work on
- Ideas get put into a single pot
- Teams draw in a random order
- Reverse order for day two
- Quantified energy savings in terms of CO2
- Leader board of improvement. Element of competition. 
- There are some tools that exist. Would need more consideration.

Final Score: 1

---

## Feedback:
> It was a touch long. At this point I am struggling to evaluate how it could be improved. Perhaps pre-canvasing the starting ideas and then groups pick/get assigned one from the list, to avoid so much duplication of aims?
- Agreed. This was intended to only last 90 minutes for an away day, it was extended to fill a larger slot at the developer meeting. That was likely an error in hindsight and should have been kept short and sweet.

> I guess there could be a better way to ensure all the ideas are unique.
- In future, this should definitely be done. Using something like slido in advance to produce a list of brainstormed ideas ahead of the actual development phase would be a very good idea.

> Can we attribute points to hackaton instead of choosing one ?
- Yes, perhaps a ranking system would be preferable for voting in future.

> How do we make the Hackathon designs available to the wider project?
- I've taken notes here, I'll post it in the `documents` directory with the other files as an `md` file. If there's anything I've missed in my notes, it would be great if they could be updated by those that came up with them. 

> When is the next hackathon?
- I suppose whenever anyone feels ready run the one they've come up with. (If you want help planning, formalising, organising, etc. please get in touch with me (Caila) on Slack)
