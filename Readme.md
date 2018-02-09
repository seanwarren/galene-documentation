Galene Documentation
====================

This repository contains documentation for [Galene](github.com/flimfit/Galene), software for motion correction of intravital FLIM data. The documentation is compiled by Sphinx using Read the Docs and is available at: http://galene.readthedocs.io/



To build and edit locally on a mac
----------------------------------
```
brew install python
pip install sphinx sphinx-rtd-theme sphinx-autobuild
make livehtml
```

To build a PDF
------------------------
```
brew cask install mactex
make latexpdf
```