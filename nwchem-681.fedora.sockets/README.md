Based on earlier work by Vladimir Konjkov

Builds a NWChem 6.8.1  binary using all modules and ARMCI_NETWORK=SOCKETS

### Build Instructions

The file Dockerfile can be used by tying the command

docker build -t  nwchem-681.fedora.sockets .

### Usage

The following command will run NWChem on 1 processor (will remove the hardwired value later ...)

docker run --entrypoint='mpirun' -v [host_dir]:/data  nwchemorg/nwchem-681.fedora.sockets nwchem [input.nw]

### Examples

#### Modifiy  mpirun options

The following command will run NWChem on 3 processors 

docker run --entrypoint='mpirun' -v /home/edo/nwchem/tests:/data nwchemorg/nwchem-681.fedora.sockets -np 3 nwchem  /data/bar_lcwpbe

Get shell on the Docker container

docker run   -v /home/edo/nwchem/tests:/data -it nwchemorg/nwchem-681.fedora.sockets
