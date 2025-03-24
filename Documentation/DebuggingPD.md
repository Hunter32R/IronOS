# Debugging PD

When using many of these soldering irons, the recommended power source is to use a USB-PD power supply.

Occasionally, issues are run into where the iron reboots or appears to not boot when connected to this supply.

There are generally a few different reasons for this to occur, the first is of course a bug or incompatibility in the IronOS PD-stack / firmware, but there are also power adaptors that either have issues or try to be _smart_ to the detrement of of compatibility.

It also helps to remember that driving a soldering iron is not like a normal load that these power supplies are designed for. Normally a laptop or phone will gently ramp the power draw up and down. Where as the soldering iron will rapidly go from 0 to full power, and then back to 0 again. This can cause issues with some power supplies tripping out.

## If the unit doesnt power up at all

This can be the most frustrating one to diagnose.

First, test the device powers up when powered by a USB-A -> USB-C cable. Or a DC power supply. This can rule out other issues that cause the device to appear off (bad flashing).

### No power
If your device wont power up on any other supply type, look into if you can boot into the bootloader. This is usually done by holding down a button while connecting it to a computer and then checking if its detected.

If the device shows up to a computer, but doesnt operate when powered up normally, the two most likely casues are a bad flash/firmware OR a non-functioning display.

Testing alternative firmware builds or trying to heat the unit (pressing the front button) can be ways to test this.

### Powers up on other supplies

If the device powers up on other supplies, but not on the USB-PD supply, it could be a problem with the USB-PD supply itself. Try using a different USB-PD supply to see if the issue persists.

If the unit does not power on any PD Supplies it could be damage to the PD PHY or the USB connector. USB-PD uses the CC pins on the connector, which are not used for normal data so a USB-A adaptor for example doesnt use these at all.

## If the unit powers up but keeps rebooting

In this case the rebooting is from the PD negotiation failing.
