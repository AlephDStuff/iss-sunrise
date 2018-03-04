# Welcome to ISS-sunrise

iss-sunrise is a plymouth animated boot screen that should work on any system that uses plymouth to display an image as the system boots and before the login screen. It is based on Earth-sunrise, but here, the earth is depicted as having lights on the ground, and when the sun rises it has a KDE logo.

## original: ubuntu-sunrise then Earth-sunrise now ISS-sunrise

This is another modification of the awesome plymouth theme made by Andre "Osku" Schmidt
This one uses actual images from the International Space Station to create the sundown and sunrise effect

## Extract the contents

Place the extracted files in your home or Desktop folder.

Open a terminal and copy and paste the following commands:

sudo cp -R iss-sunrise/ /usr/share/plymouth/themes/

sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/iss-sunrise/iss-sunrise.plymouth 100

sudo update-alternatives --config default.plymouth #here, choose the number of the theme you want to use then hit enter

sudo update-initramfs -u

Reboot... your system should be running the new theme.

## code notes
## ==========

the "offset" variable is used to set the y position of the planet top. 
0 would be center, positive values go down and negative to top of screen.
(all parts should use this offset)

if you scroll past the image/sprite definitions, you see some *.start and
*.end values. those say at which "progress-time" (from 0 to 1) that part
will be faded in. 

sunGlow also has .animStart/End "progress-time", to say when to move from
.startPos to .endPos on the screen
