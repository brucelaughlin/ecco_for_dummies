# ecco_for_dummies
Exploring how to get started with and use ECCO, as a computer novice

This is intended to supplement the ECCO tutorial.  We'll use some things from it, and we'll add our own examples to
hopefully get you up to speed quickly and easily.

So, we will be referencing the tutorial a few times, but not following it exactly.  Find it here:

https://ecco-v4-python-tutorial.readthedocs.io/Tutorial_wget_Command_Line_HTTPS_Downloading_ECCO_Datasets_from_PODAAC.html


OK, to begin:

Make a new directory (aka folder) that you'd like to use for the explorations we'll do here.

For example, on your desktop, make a new directory called "exploring_ecco".  We'll use that as our example here.

Open up a terminal, and navigate to that directory:

cd ~/Desktop/exploring_ecco



Create a file that we'll use to store the list of file urls that we want to download:

touch files_to_download.txt


Now that empty file exists, and we'll use it later.




NOW,

to download ECCO output files (which are netCDF files ending in ".nc", which are also called "granules"):


You should follow step 1 in the tutorial, but with a warning: the password you choose for your Earthdata account will be
publicly visible in the file you need to make in step 2.  So, ... maybe don't use a password that you use elsewhere in your
life, since you might view this file in front of someone.

So, anyway, FOLLOW STEP 1 IN THE TUTORIAL, and consider heeding the warning printed above this line. 


Then, FOLLOW STEP 2 IN THE TUTORIAL.  This is where the warning for step 1 of the tutorial comes into play.



Then, once your Earthdata account is activated, log in!  aka, visit:

https://search.earthdata.nasa.gov/

and log in with your username and (hopefully different than passwords you hope to keep secret forever) password.


In the search bar, type "ecco", and press enter


OK, now you're going to have to have a little faith, because we'll be clicking buttons that say "download" a few times,
but they don't actually download anything (unless you click the final download button!).  Sounds scary, but just follow
these steps:


Click on the first "matching collection" shown to the right of the search bar, 

(like "ECCO Ocean Temperature and Salinity - Monthly Mean llc90 Grid (Version 4 Release 4)")


Then click the "Download All" button at the bottom right (this won't download anything yet)


Then click the "Downlaod Data" button at the bottom left (this also won't download anything yet)


AFTER THIS, DON'T CLICK ANYTHING SAYING DOWNLOAD ANYMORE!  at least, if you want to do things the way we're describing here.


Then click "Expand" (it's the button next to "Download Files", which you DON'T want to click, unless you wanna download everything listed below)


Now for some trickery:

move your mouse just to the left of the the first "h" in the url of the first file listed (ie just to the left of "https://......")

then scroll down to the bottom

then hold SHIFT, and click again to the right of the last thing you see in the list of urls

hopefully this highlights all of the urls in this list, and nothing else.

if that worked, then press "ctrl + c" to copy what you've highlighted (or use right click -> copy, or however you can copy)



THEN, 

open the file you made, ie:

vi files_to_download.txt


or you can even just open it with your mouse, if it's on your desktop or if you can find where you made it.

and paste the list of urls into the file

(if you used vi to open the file, enter "insert mode" by pressing "i", and then paste (ctrl + v or however you do it), hopeuflly that works...)


Then save the file and exit

RECOMMENDED:

If the text file you just made has a ton of lines, you can open it again and delete all but the first 10 (for example), by 
navigating to line 11 and typing (1000 dd), which will delete from the current line down 1000 lines, or to the end of the file.



Ok, NOW, exit text the file, and create a directory for storing the ECCO granules you're about to download:


mkdir granules

Now, run the following command in the terminal:

wget --no-verbose --no-clobber --continue -i files_to_download.txt -P granules


If it works, all of the urls listed in "files_to_download.txt" will be downloaded into the "granules" directory.

More to come soon!





