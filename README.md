# install-ferret-notes

for unix systems

Installing Ferret (NOAA) onto Ubuntu

Ferret is an application produced by the NOAA .  It is an interactive computer visualization and analysis environment used by Geographers and the like. This is how I installed it onto Ubuntu 10+ and my notes from following their install guide.

Download the three files into a know location.  I keep all my software files together so inside my software folder I created a new folder called ferret and used wget to grab copies. This means I have a record of what files and versions I’m using:


1
2
mkdir -p ~/software/ferret
cd ~/software/ferret
These are links to the 32bit versions. You are advised to check that this is what you want and that the 64bit versions would suit your system better – see note at bottom. I use wget to grab these.

Ferret Executables
Ferret Environment
Ferret Datasets
Change to the recommended install location and create a new folder called ferret and step into this folder. You will probably need to SUDO from this point on.


1
2
3
cd /usr/local
mkdir ferret
cd ferret
Installing the Support Files

Now you need to extract the support files into the ferret folder you just created. Type:


1
sudo tar -xzf ~/software/ferret/fer_environment.tar.gz
where ~/software/ferret/ is replaced with the location you saved the original download files in. Doing a ls in that folder should now give you the following listing – different to what is given on the NOAA install pages.

bin contrib examples ext_func go ppl

Now you need a location to store the sample files for ferret and should extract them from the downloads location.

mkdir ~/fer_data
cd ~/fer_data
sudo tar -xzf ~/software/ferret/fer_dsets.tar.gz

which should give you:

data descr grids

Installing Ferret

You should now be able to install ferret using a supplied script. If you have followed the instructions above you can run.


1
sudo /usr/local/ferret/bin/Finstall
And make the following choices:

Click 1
Enter the following for FER_DIR:  /usr/local/ferret
Enter the full path to the /software/ferret folder.  This means you cannot use ~ but would need to give the full path e.g. /home/username/software/ferret
Customizing the Paths

To customize the paths so Ferret knows where to find everything we must do the following:

Click 2
Enter /usr/local/ferret as the FER_DIR if you followed the instructions above.
Enter /home/username/fer_data as FER_DSETS if you followed the instructions above.
Provide a location for the creation of ferret_paths file e.g. /usr/local
Lastly you need to add the required paths to your bash path profile by running the script created in the previous section. Type:


1
source /usr/local/ferret_paths
at the command line where /usr/local was the location selected above for the path files. You should now be able to run Ferret with the ferret command. Success should equal something like:


1
2
3
4
5
6
NOAA/PMEL TMAP
FERRET v6.71
Linux 2.6.32-131.6.1.el6.x86_64 32-bit - 08/08/11
30-Aug-11 10:31
 
yes?
Type quit to exit.
