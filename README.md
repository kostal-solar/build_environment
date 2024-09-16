**COPYRIGHT (c) 2024 Kostal-Industrie-Elektrik GmbH & Co. KG**

Author: Markus Rübesam <m.ruebesam@kostal.com>

## Build environment for Inverter User Interface embedded Linux (Yocto based)

Setup tested with Ubuntu 18.04 LTS running @ WSL2 under Windows 11.

### Setup the build environment:
``sudo apt-get update``

``sudo apt-get install git docker chrpath diffstat python3 python3-pip``

### Setup KAS:
``cd to your preferred kas folder for installing/downloading kas``

``git clone https://github.com/siemens/kas.git``

``sudo pip3 install distro jsonschema kconfiglib PyYAML git``

>*in case of errors using sudo and/or pip3 use following command:*
>
>``pip install --trusted-host pypi.org --trusted-host pypi.python.org --trusted-host files.pythonhosted.org pip setuptools``

``cd kas/``

``sudo pip3 install .``

>``kas --version`` *(should work now...)*

### Build an image

``cd to your preffered location for cloning the repo and building the image``

``git clone https://github.com/kostal-industrie/build_environment.git``

``cd build_environment``

``kas shell doc/project.yml``

>within the buildfolder (kas will automatically switch there) run:
>
>``bitbake kie-image-base-swu``
>
>After building you find the image in build/tmp/deploy/images/mx6ul-kie-inverter/kie-image-base-swu-mx6ul-kie-inverter-*DATE_&_TIME*.swu
