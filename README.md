Setup tested with Ubuntu 18.04 LTS running @ WSL2 under Windows 11.

### Setup the build environment:
1. sudo apt-get update
2. sudo apt-get install git docker chrpath diffstat python3 python3-pip

### Setup KAS:
1. cd to your preferred kas folder for installing/downloading kas
2. git clone https://github.com/siemens/kas.git
3. sudo pip3 install distro jsonschema kconfiglib PyYAML git
4. cd kas/
5. sudo pip3 install .

kas --version
should work now...

### Build an image

1. cd to your preffered location for cloning the repo and building the image
2. git clone KOSTAL OS BUILD ENV from github
3. cd build-environment

4. kas shell doc/project.yml
5. bitbake kie-image-base-swu
or
4. kas build doc/project.yml

After building you find the image in build/tmp/deploy/images/mx6ul-kie-inverter/kie-image-base-swu-mx6ul-kie-inverter-$DATE&TIME$.swu
