# Installing DeepChem on Vagrant

Instructions for installing deepchem into a 
vagrant box (VirtualBox image) running
Ubuntu Xenial (16.04).

## Vagrant Box Setup

On host machine, create a new vagrant box:

```
vagrant init ubuntu/xenial64
```

Edit the Vagrantfile to pass port 8888 on the 
vagrant (guest) machine (which is the Jupyter 
notebook port) on to port 8889 on the host machine:

```
Vagrant.configure("2") do |config|

  # Map port 8888 (vagrant) to port 8889 (host)
  config.vm.network "forwarded_port", guest: 8888, host: 8889

  # Create shared folder (host deepchem/ --> guest /tmp/deepchem)
  config.vm.synced_folder "deepchem/", "/tmp/deepchem"

end
```

Bring the machine up:

```
vagrant up
```

Get ssh info:

```
vagrant ssh-config
```

Or just ssh in:

```
vagrant ssh
```

## Install Miniconda on Vagrant Box

Install Miniconda on the Vagrant box:

```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
chmod +x Miniconda*
./Miniconda3-latest-Linux-x86_64.sh
```

## Install DepeChem on Vagrant Box

Install DeepChem on the Vagrant box:

```
conda install -y -c deepchem -c rdkit -c conda-forge -c omnia deepchem=2.1.0
```

## Start Jupyter Notebook

After you have installed DeepChem, you should have
Jupyter available on the command line from inside
the vagrant box:

```
which jupyter
```

Start up the jupyter notebook:

```
jupyter notebook
```

## Stop Vagrant Box

Close the ssh shell and shut down the vagrant machine 
by running this command on the host machine:

```
vagrant halt
```

## Destroy Vagrant Box

Destroy the vagrant machine. Start by checking its name:

```
vagrant status
```

The machine is probably called `default`. Destroy the 
default machine:

```
vagrant destroy default
```


