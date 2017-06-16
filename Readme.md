To build and edit locally on a mac:

brew install python
pip install sphinx sphinx-rtd-theme sphinx-autobuild

make livehtml


To build the PDF version:

brew cask install mactex
make latexpdf