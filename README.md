# smc_util
Apple System Management Control (SMC) utility

Forked from original smc_util repository, with a couple of other, slightly modified, SMC-related tools:
* powermetrics.d from https://gist.github.com/beltex/acbbeef815a7be938abf
* SmcDumpKey.c from https://www.contrib.andrew.cmu.edu/~somlo/OSXKVM/

# How to use

Chances are you're here because of my [blog post](https://floe.butterbrot.org/matrix/hacking/tdm/) or [SO question](https://stackoverflow.com/questions/43491594/reverse-engineering-the-target-display-mode-on-an-imac/), and want to use this to turn an old iMac running Linux into a display.

Note: I don't have the iMac I used for this anymore, so I can't test anything, sorry. That being said, the steps to use this are (on Ubuntu and derivatives):

```
sudo apt-get install build-essential
git clone https://github.com/floe/smc_util.git
cd smc_util
make
sudo ./tdm_on.sh # enable target display mode
sudo ./tdm_off.sh # disable target display mode
```

IMPORTANT: when you run `tdm_on.sh` and it works on your iMac, then the display will switch over to the DP input and you won't have the console anymore. Make sure you have a remote shell open first, or maybe a keyboard hotkey set up, so you can also run `tdm_off.sh` again to switch back to the internal iMac graphics.
