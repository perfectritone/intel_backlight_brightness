intel_backlight_brightness
==========================

Bash script for screen brightness on Lenovo ThinkPad E530. This script can be called from the command line or by being bound to a key.

To use
------

With Openbox this is accomplished by adding the following to the rc.xml file

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

You may need to change the permissions of the brightness files to allow changes by the local user.