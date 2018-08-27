OpenSC nightly builds are available in seperate branches organized by their git identifier. The latest build can be downloaded as follows:

```sh
# Get OpenSC
git clone https://github.com/OpenSC/OpenSC --single-branch
cd OpenSC

# Get name of branch in Nightly which corresponds to the latest commit in OpenSC
BRANCH=`git log --max-count=1 --date=short --abbrev=8 --pretty=format:"%cd_%h"`

# Download the build
wget https://github.com/OpenSC/Nightly/archive/${BRANCH}.zip

# Unpack the build
unzip ${BRANCH}.zip
```

Single build artifacts may be downloaded using the web interface:
```sh
# Open the build in Firefox
firefox https://github.com/OpenSC/Nightly/tree/${BRANCH}
```

Note that old builds may be deleted at any time.
