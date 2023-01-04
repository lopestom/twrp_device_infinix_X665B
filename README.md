# TWRP device tree for Infinix Hot 12i (X665B) - MT6761 - A11

## Status

Specs [here](https://www.gsmarena.com/infinix_hot_12i-11473.php)

The tester [s.777](https://4pda.to/forum/index.php?showuser=4635974) only install `boot-x665B-A11-nnnnnnn-nnn.img` test modified file to know if TWRP can start.

Some tests was made:

Issue: 

New file with new version TWRP3.7.0_11: Need test after 2023-01-01
Two files compiled. The first file tested/started by s.777 and have no touch screen. The drivers of these's located in the \vendor\firmware\novat* but TWRP has that issue. Maybe modules (\lib\modules) need putting in the DT too but need more tests.
The second file created with A11 branch so is not tested since 2023-01-03 and have minimal files so not enc_dec mode. The new file copied to \vendor\firmware\gt1151_default_firmware2.img for test touch drive.
I think is need put the flag to test about issue with touch screen:
```
# Try disabling the screen timeout. It is not a fix, but it can be an effective work-around.
TW_NO_SCREEN_TIMEOUT := true
```
But I'm waiting the test of second file in this moment.

****2022-10-12****: Changes to made new version TWRP3.x.x

### This branch android-11 has ***encrypt/decrypt*** files and option to more test with that.

![Infinix Hot 12i](https://fdn2.gsmarena.com/vv/pics/infinix/infinix-hot-12i-1.jpg)

-----

![TWRP Working](https://github.com/lopestom/twrp_device_infinix_x697/blob/android-11/picture/TWRP-IN_11_Pro-MT6871.png?raw=true)

-----
#### Building

```bash
source build/envsetup.sh
lunch twrp_x665b_h6222-eng
mka bootimage
```

