# Script to swap between noveau and nvidia drivers

# Purpose

My setup is weird. It is a laptop with HDMI and a 1050Ti, I use my TV and I sit across the room with a wireless keyboard. I need noveau for Minecraft and nvidia for literally everything else. I could make separate grub entries, one that loads nvidia and one that loads nouveau, but then I'd have to get up and fiddle with my laptop since grub doesn't have bluetooth support. Which, why would I want to do that? Plus, I'm already doing that to switch between the displays that I want to use in the console, so I'd have to maintain 4 boot entries plus my rescue one.

By the way this is the first project where I've actually documented what I'm doing. I'd expect some for st-organise-photos and st-collate-music, because those are my real hobby projects. edid-suite requires me to learn algorithms etcetera rather than design it.

# Design requirements

1. Reliably toggle between the modules
   1.1. User expected to disable DM and log out of graphical session manually (I do not have a DM—only design to what you need)
       1.1.1. What kind of error checking and message can we add?
       1.1.2. Reminder at the end of the script to start the DM. Maybe we an tail the bash history for flair
   1.2. Do not hardcode PCI numbers: how can we find them? /sys/device/virtual/virtualterminal/vtcon0/subsystem/device or something?
       1.2.1. lscpi: check dependency BEFORE starting

3. Some kind of fallback function that we run if we get an error message to try recover?
    2.1. run || fallback

# Examples

https://www.reddit.com/r/archlinux/comments/mh8n8r/creating_script_to_change_between_nvidia_and/
https://unix.stackexchange.com/questions/219059/remove-nouveau-driver-nvidia-without-rebooting
https://dassencio.org/75
https://askubuntu.com/questions/16998/switch-between-nvidia-current-and-nouveau-without-a-reboot

# Roadmap

I really need to focus on school for the next week. Like it's a real make-or-break thing. So expect no more commits until then.
