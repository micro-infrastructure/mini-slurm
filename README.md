# Mini-SLURM

Mini-SLURM is a slurm cluster in a VM. It sets up a VM on virtualbox and start slurm container/s provided by [xenon-slurm](https://github.com/xenon-middleware/xenon-docker-images.git) 

## Installation
- Install Vagrant, VirtualBox,  GIT for Ubuntu:

`apt-get install vagrant virtualbox git`
- Clone the mini-slurm

`git clone --branch 0.1.2 https://github.com/micro-infrastructure/mini-slurm.git`
- Provision VM. 

`cd mini-slurm`
`make build`

- SSH to slurm cluster
`ssh xenon@192.168.50.11`

- Password and slurm commands are given [here](https://github.com/xenon-middleware/xenon-docker-images/tree/master/slurm-17)
- You can suspend and resume the VM using

`make pause`
`make resume`

- To destroy the VM

`make clean`
