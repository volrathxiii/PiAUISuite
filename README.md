# About This Fork
This fork is based on StevenHickson/PiAUISuite which is awesome! I have slightly configured it to work with pico text-to-speech instead of googles. And setup a php-based voice command processor. The cool thing about having a php processor is that you can have a web based tool incase voice command fails. So be sure to checkout https://github.com/volrathxiii/Avy as well.

## How to install

To install the dependencies, run:
```bash
sudo apt-get install -y libboost-dev libboost-regex-dev youtube-dl axel curl xterm libcurl4-gnutls-dev mpg123 flac sox
```

To install PiAUISuite:
```bash
git clone https://github.com/volrathxiii/PiAUISuite.git
cd PiAUISuite/Install
./InstallAUISuite.sh
```

It will:
* ask if you want to install the dependencies
* to install each script

### How to install Pico
http://rpihome.blogspot.com/2015/02/installing-pico-tts.html


Copyright

[GPLv3](https://tldrlegal.com/license/gnu-general-public-license-v3-(gpl-3))

Steven Hickson


