#workshop #documentation #mantidDevMeeting2023 
## Options
- Online Docs Only, No docs Package: Saves Full 200MB
	- Some don't have the internet, and is those who may need it most
- Docs Package Not a Workbench Requirement: Saves 0 or 200MB
- Ship HTML files only, not QtAssistant, browser opens docs: Saves ~100MB 
	- Also works on the windows conda install
- Stop generating the dialog box screenshots: Save 70MB
       - Add option to shinx plugin to optionally turn off/on creating a dialog for individual algorithms

## Resulting Tasks
- Move to [`graphviz`](https://www.sphinx-doc.org/en/master/usage/extensions/graphviz.html) plugin on Sphinx for plotting
- Use [`bibtex`](https://www.sphinx-doc.org/en/master/usage/extensions/graphviz.html)for referencing

## Notes
### Sizes
- Out of ~200MB, 176MB are images, 70MB is dialog boxes
- HTML 264MB (Images 170MB)
- 3.4MB GIF in there 
- How many images are needlessly large?
- Qt Webkit takes up a decent chunk of space
### Online Docs
- Why not link to the online docs?
	- Bundling docs ensures matching of docs
	- Docs are archived in each release
	- Internal browser means you get one space to load all of them
- Qt assistant doesn't understand JS, so can't use plotly or mathJax? 
	- Assistant uses ping
- not all instrument cabin machines have web access to mantidproject.org
- Reasons to use the Web Version
	- Forward & Back works
	- MathJax looks better on the web
- Need to ensure the link goes to the right release version
#### Facility Implementation
- IDAaaS:
	- Guaranteed internet connection
	- Why deploy the docs?
- SNS:
	- Firewalled off instrument machine
	- Mantid installed on one machine, access gained to that one from the instrument cabins
	- `rsync`
### Generated Dialog Images
- Algorithm Dialog
	- Scientists like it (anecdotally)
	- Creates a lot of images
- Replacement for Dialog Box Images:
	- Is the title enough?
- Can we lazily
- 

### Installation
- Choosing whether to install the docs
	- On install?
	- When requested?
### Startup

- Stopping calls out to web if any of the checks fail 
### Misc
- Just remove it for a release? Judge response. 
- Help has never worked on a conda install on windows

