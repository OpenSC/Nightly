OpenSC nightly builds are available in seperate branches organized by their git identifier. The latest build can be downloaded as follows:

```sh
# Get OpenSC
git clone https://github.com/OpenSC/OpenSC --single-branch
cd OpenSC

# Get name of branch in Nightly which corresponds to the latest commit in OpenSC
BRANCH=`git log --max-count=1 --date=short --abbrev=8 --pretty=format:"%cd_%h"`

# Download the build
curl https://github.com/OpenSC/Nightly/archive/${BRANCH}.zip -L --output ${BRANCH}.zip

# Unpack the build
unzip ${BRANCH}.zip
```

Single build artifacts may be downloaded using the web interface:
```sh
# Open the build in Firefox
firefox https://github.com/OpenSC/Nightly/tree/${BRANCH}
```

Some build artifacts may be split up into multiple chunks due to file size limitations. The chunks have extensions in alphabetic order (`.aa`, `.ab`, ...). To concatenate them, use something like the following in a terminal:
```sh
# Recreate the macOS image
cat OpenSC*.dmg.* > OpenSC.dmg
```

```cmd
# Recreate the Windows debug symbols
copy /b OpenSC-0.21.0-rc1_win64-Debug.zip.aa+OpenSC-0.21.0-rc1_win64-Debug.zip.ab OpenSC-0.21.0-rc1_win64-Debug.zip
```

Note that old builds may be deleted at any time.
