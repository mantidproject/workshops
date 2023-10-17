#workshop #mantidDevMeeting2023 

## Options
- Add functionality to the [issue on the conda repo](https://github.com/conda/conda/issues/8089)
- Have a single main dependencies file and then 3 specific ones for each OS. 
	- When activating the environment, both files need to be given in the command
	- `conda env create -f mantid-developer.yml -f mantid-developer-osx.yml`
	- Work in progress on the `simplify_dev_envs` branch
## Notes
- Want to edit the dependencies in one place, not four. 
	- 3 developer files and one package file
	- Should all be the same, but may not be if something isn't updated properly on anaconda
	- Precommit check/directive to generate OS specific `.yml` from a central file.
	- Some specific packages are for a single OS
	- 
- Algorithms that depend on external libs that don't normally ship with mantid
	- `.rst` files aren't generated and tests aren't run on these algorithms on the build servers (maybe are?)
	- Set as build dependencies? 
	- 