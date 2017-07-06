# SdFat
Just the library portion of greiman's SdFat repo

## Use with the rest of greiman's SdFat repo
Cloned here at [link] https://github.com/systronix/SdFat_greiman
with original at [link] https://github.com/greiman/SdFat

## Some examples modified to run on SALT
Some examples are in the private repo ...SALT2-TEST but at this moment there is a SS issue, see *Issues* below

### Issues
- Initially we were not sure how to change uSD CS. Now we use
	```
	const uint8_t SD_CHIP_SELECT = 15;
	```
	which seems to work fine
- On SALT 2.2 #2/4 the uSD socket is not quite right: it doesn't always fully eject the uSD card, which in turn prevents it from pushing in and latching fully. This may be a factor in unreliable uSD access just on this system.
 - sometimes SALT_reptile can't init the uSD
 - card runs SdInfo fine on another SALT 2.2 board
 - file structure seems to be corrupted such that reptile can't create a new folder or file for logging. Reformatting the card fixed that.
 - TotalPhase beagle SPI sniffer shows partial last byte errors at the end of a SPI message. This means, apparently, that CS negated before all the bits were clocked on MOSI and MISO. What could possibly cause this? I never see this on Ehternet SPI, just uSD SPI.