# SdFat
Just the library portion of greiman's SdFat repo

## Use with the rest of greiman's SdFat repo
Cloned here at [link] https://github.com/systronix/SdFat_greiman
with original at [link] https://github.com/greiman/SdFat

## Some examples modified to run on SALT
Some examples are in the private repo ...SALT2-TEST but at this moment there is a SS issue, see *Issues* below

### Issues
There is an issue changing SS, the SPI slave select used by the SD Card. We have not figured how to properly do this and it is causing SD card access failures in some example programs such as SdInfo. It is also causing issues in the uSD card use on SALT, particularly in loading .ini config files from a card.
