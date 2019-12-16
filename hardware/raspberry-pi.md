# Raspberry Pi





### Hardware Overheating

Some blockchain operations can be quite intensive, resulting in overheating of the Raspberry Pi's hardware.

If you see a thermometer icon appear in the top right-hand corner of the Pi's screen, the system is automatically slowing down to compensate for overheating.  Try improving the board's ventilation or adding a heatsink or fan.  Alternatively, see what's creating all of that heat by inspecting your running processes with `top` or `htop`.  Reduce the computing load on the Pi and that should fix the overheating within a few seconds to a minute.

To see the current temperature of the Pi's SOC, run this command:

`vcgencmd measure_temp`

The Raspberry Pi starts throttling itself at 80°C.

References:

* [https://www.raspberrypi.org/documentation/configuration/warning-icons.md](https://www.raspberrypi.org/documentation/configuration/warning-icons.md)
* [https://www.raspberrypi.org/forums/viewtopic.php?t=181972](https://www.raspberrypi.org/forums/viewtopic.php?t=181972)

### Video Configuration

If you are running a Raspberry Pi without a GUI and using the command line interface directly by connecting it to a monitor, you can change the display resolution by editing `/bootconfig.txt`**:**

```text
gpu_mem=128
hdmi_group=1
hdmi_mode=4
```

To see the available resolution and how they may to `hdmi_group` and `hdmi_mode`:

* [https://www.raspberrypi.org/documentation/configuration/config-txt/video.md](https://www.raspberrypi.org/documentation/configuration/config-txt/video.md)





