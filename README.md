NativeCAM for LinuxCNC - realtime CAM

This is reading for any installer.

Clone or extract in a ~/sub-directory of your choice with read/write rights.

Open a terminal window in the same directory.

Make sure these files are executabbes :
	ncam.py
		
You need to install python-lxml if not allready installed, the command is :
	sudo apt-get install python-lxml

1.	Simple usage - Stand alone mode
--------------------------------------------------------------------------------
1.	 Copy then paste one of these commands :

	for mill : 
	./ncam.py -iconfigs/sim/axis/ncam_demo/mill.ini -cmill ; 
	./ncam.py -iconfigs/sim/axis/ncam_demo/mill-mm.ini -cmill ; 

    for plasma : 
	./ncam.py -iconfigs/sim/axis/ncam_demo/plasma.ini -cplasma ;
	./ncam.py -iconfigs/sim/axis/ncam_demo/plasma-mm.ini -cplasma ;

	However it is not meant to be usefull stand alone unless LinuxCNC
		was/is loaded with the right SUBROUTINE_PATH


2.	Best way - Run embedded
--------------------------------------------------------------------------------
1.	Issue / copy then paste the following command
	
	sudo python nondeb_setup.py
	
	This will create required links and modify files.
	You do not do this more than once except maybe after lcnc updates
	because it will replace the files and erase the link,
	until NativeCAM is integrated in the distribution
	To restore the system, simply issue the command : 'sudo python nondeb_setup.py c'

	Run first with : ./ncam.py -h

2.	Start LinuxCNC with one of these commands (copy/paste) :

	for mill : 
	(axis interface)
	linuxcnc configs/sim/axis/ncam_demo/mill.ini ; 
	linuxcnc configs/sim/axis/ncam_demo/mill-mm.ini ; 
	
	(gmoccapy interface)
	linuxcnc configs/sim/gmoccapy/ncam_demo/mill.ini ; 
	linuxcnc configs/sim/gmoccapy/ncam_demo/mill-mm.ini ; 

    for plasma : 
	(axis interface)
	linuxcnc configs/sim/axis/ncam_demo/plasma.ini ;
	linuxcnc configs/sim/axis/ncam_demo/plasma-mm.ini ;
	
	(gmoccapy interface)
	linuxcnc configs/sim/gmoccapy/ncam_demo/plasma.ini ;
	linuxcnc configs/sim/gmoccapy/ncam_demo/plasma-mm.ini ;

3.	Open a project in the examples directory
	
	for mill : 
	Basic spacer.xml ; 
	Fun wheel demo.xml ; 

	for plasma :
	plasma test.xml ;
	plasma demo.xml ; 

	
3.	Tutorials
--------------------------------------------------------------------------------
1.	Use menu help->NativeCAM on YouTube
	
	or follow this link
		
	https://www.youtube.com/channel/UCjOe4VxKL86HyVrshTmiUBQ


4.	Translation
--------------------------------------------------------------------------------
1.	Under development
	

5.	Setting-up your own file
--------------------------------------------------------------------------------
1.	Open a terminal in your inifile directory
2.	Type : path_to_prog/ncam.py --ini=inifilename --catalog=(mill | plasma | lathe)
3.	Your .ini file will be modified and necessary files copied
4.	Start LCNC with : linuxcnc inifilename
