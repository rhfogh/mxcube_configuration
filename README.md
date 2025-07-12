# mxcube_configuration
Demo and shared configuration files for mxcubeweb and mxcubeqt projects

The files in this repository are licensed under the LGPL version 3 license,
As specified in  the COPYING.LESSER file.

The demo.yaml/ directory contains configuration files for the demo ('mockup')
version of MXCuBE. 

### Organisation

Files specific to mxcubeqt are in the mxcube-qt subdirectory

Files specific to mxcubeweb are in the mxcube-web subdirectory

Files in the gphl directory are for the Global Phasing workflow program,
and work with either implementation.

Files directly in demo.yaml/ are shared between implementations. 
Note that beamline_config.yml is shared between both implementations,
so that also implementation-specific files must have names that match 
those in beamline_config.yml.

### Usage

To use this repository you must run MXCuBE using a configuration repository lookup path, as follows:

#### mxcubeweb:

Normal operation:

mxcubeweb-server -r .../mxcube_configuration/demo.yaml/mxcube-web/:.../mxcube_configuration/demo.yaml/  ...

With GPhL workflow:

mxcubeweb-server -r .../mxcube_configuration/demo.yaml/gphl:.../mxcube_configuration/demo.yaml/mxcube-web/:.../mxcube_configuration/demo.yaml/  ...


#### mxcubeqt:

Set the environment variable MXCUBE_CORE_CONFIG_PATH to

Normal operation:

".../mxcube_configuration/demo.yaml/mxcube-qt:.../mxcube_configuration/demo.yaml"

With GPhL workflow:

".../mxcube_configuration/demo.yaml/gphl:.../mxcube_configuration/demo.yaml/mxcube-qt:.../mxcube_configuration/demo.yaml"

And then run (e.g.)
python .../mxcubeqt/mxcubeqt/__main__.py --pyqt5 --mockupMode --coreConfigPath "${MXCUBE_CORE_CONFIG_PATH}"