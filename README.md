**COPYRIGHT (c) 2024 KOSTAL Solar Electric GmbH**

Author: Markus Rübesam <m.ruebesam@kostal.com>

## Disclaimer of Warranty.

THERE IS NO WARRANTY FOR THE PROGRAM, TO THE EXTENT PERMITTED BY APPLICABLE LAW. EXCEPT WHEN OTHERWISE STATED IN WRITING THE COPYRIGHT HOLDERS AND/OR OTHER PARTIES PROVIDE THE PROGRAM “AS IS” WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE. THE ENTIRE RISK AS TO THE QUALITY AND PERFORMANCE OF THE PROGRAM IS WITH YOU. SHOULD THE PROGRAM PROVE DEFECTIVE, YOU ASSUME THE COST OF ALL NECESSARY SERVICING, REPAIR OR CORRECTION.

## Limitation of Liability.

IN NO EVENT UNLESS REQUIRED BY APPLICABLE LAW OR AGREED TO IN WRITING WILL ANY COPYRIGHT HOLDER, OR ANY OTHER PARTY WHO MODIFIES AND/OR CONVEYS THE PROGRAM AS PERMITTED ABOVE, BE LIABLE TO YOU FOR DAMAGES, INCLUDING ANY GENERAL, SPECIAL, INCIDENTAL OR CONSEQUENTIAL DAMAGES ARISING OUT OF THE USE OR INABILITY TO USE THE PROGRAM (INCLUDING BUT NOT LIMITED TO LOSS OF DATA OR DATA BEING RENDERED INACCURATE OR LOSSES SUSTAINED BY YOU OR THIRD PARTIES OR A FAILURE OF THE PROGRAM TO OPERATE WITH ANY OTHER PROGRAMS), EVEN IF SUCH HOLDER OR OTHER PARTY HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGES.

## Build environment for Inverter User Interface embedded Linux (Yocto based) - Build instructions

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
