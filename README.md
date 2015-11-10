upd
===

Ubuntu Personal Desktop - First installation

This project is an installation tool which installs and configures the basics on a Ubuntu pesonal desktop. As your disk can be crashed or deleted, I prefer to be sure that I can repeat the exact same configuration. See following the details.
* Creation of a system group
* Creation of my own user to avoid the usage of root
* Installation of the packages in the package.lst
* Installation of aliases I like to use

## Installation and use
With a root profile, create a directory and put the updInstaller in it, then launch the updInstaller.
The retrieving is a wget instead of a git something because git is not installed at this moment !

#### If you were me
Just copy/paste and launch the 2 lines below, and you will install the exact same configuration than mine.

    wget -r --no-check-certificate https://github.com/oloc/Ubuntu-Personal-Desktop/archive/master.tar.gz -O /tmp/master.tar.gz 
    tar -xvf /tmp/master.tar.gz -C /tmp && /tmp/Ubuntu-Personal-Desktop-master/updInstaller

#### If I were you
I suggest to retrieve the stuff and tweak some parts.

    wget -r --no-check-certificate https://github.com/oloc/Ubuntu-Personal-Desktop/archive/master.tar.gz -O /tmp/master.tar.gz 
    tar -xvf /tmp/master.tar.gz -C /tmp

Here you have to modify with your own choices the files:
* updInstaller.cfg 
* aliases.cfg
* var.cfg
* The target of the \<PackageList\> link in the \<PkgDir\>
Then you launch the updInstaller and you can go take a mug of coffee in order to wait the job:

     /tmp/Ubuntu-Personal-Desktop-master/updInstaller

## To know
All the hardcasted definition are in the updInstaller.cfg. I mean the files name, the directories location, the group and the user.

The \<PackageList\> (the link named current in this version) is the list of the packages to install (surprised !?). If a package need a specific way to be installed, you can create a \<package name\>.inst in the \<InstDir\> and script on it. See the rvm example.
The \<AliasesList\> (aliases.cfg in this version) is the file with the aliases added to the created user. Same for the \<GlobalsList\> (var.cfg in this version) which contains the globale variables to set with the created user. Actually these files are put in the \<ComDir\> and a .bash_aliases is set as it should be to take them into account.




