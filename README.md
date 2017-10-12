intel_backlight_brightness
==========================

Shell script for screen brightness on Lenovo ThinkPad E530. This script can be called from the command line or by being bound to a key.

To use
------
You may need to change the permissions of the brightness files to allow changes by the local user.
     sudo chmod +020 /sys/class/backlight/intel_backlight/brightness
     sudo chgrp wheel /sys/class/backlight/intel_backlight/ -R

Place the script, or add a link to ~/scripts/brightness.sh

### Openbox
Add the following to your rc.xml

    <keybind key="XF86MonBrightnessUp">
      <action name="Execute">
        <startupnotify>
          <enabled>true</enabled>
          <name>brighter</name>
        </startupnotify>
        <command>/home/aura/projects/brightness.bash +</command>
      </action>
    </keybind>
    <keybind key="XF86MonBrightnessDown">
      <action name="Execute">
        <startupnotify>
          <enabled>true</enabled>
          <name>dimmer</name>
        </startupnotify>
        <command>/home/aura/projects/brightness.bash -</command>
      </action>
    </keybind>

### sxhkd
Add the following to your sxhkdrc

XF86MonBrightnessUp
  ~/scripts/brightness.sh +
XF86MonBrightnessDown
  ~/scripts/brightness.sh -

