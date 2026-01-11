# Fedora Debloat Guide
Welcome to your fresh Fedora GNOME setup! You’ve probably noticed that Fedora comes packed with a lot of preinstalled software. While that’s great for some people, a lot of it just isn’t necessary for others.

This guide is for anyone who wants to clean up their Fedora setup by removing what they don’t need. It’s not about getting rid of everything; it’s about getting rid of the stuff you don’t need. Everyone has different needs, so if you use something I mention here, feel free to keep it. This is just what worked for me.

> [!WARNING]
> This isn’t official Fedora documentation but just a collection of tweaks that worked for me. You’re mostly removing apps and services you don’t need, but proceed with caution. If something goes wrong (unlikely, but still), I’m not responsible. Feel free to ask for help on the [Fedora forums](https://discussion.fedoraproject.org/)!
#
### Revert Changes
For every change, I’ll provide the command to undo it. So if you remove something and later realize you need it back, just run the restore command.

> [!NOTE]
> When removing packages, DNF might want to pull out other stuff that depends on them. Always read what it's planning to do before you hit yes. If you want to stop it from auto-removing extras, add --noautoremove to the end of the remove command.
```
sudo dnf remove <package> --noautoremove
```
#
### Remove extra input methods
These input methods are for typing in different languages. If you only use English (or your main language), you can safely remove them.

Packages:
- ibus-m17n
- ibus-typing-booster
- ibus-hangul (Korean)
- ibus-libpinyin (Chinese)
- ibus-anthy (Japanese)
```
# Uninstall
sudo dnf remove ibus-m17n ibus-typing-booster ibus-hangul ibus-libpinyin ibus-anthy

# Restore
sudo dnf install ibus-m17n ibus-typing-booster ibus-hangul ibus-libpinyin ibus-anthy
```

> If you ever need to check or adjust input methods, you can find these in the Software app under Input Sources at the bottom.
#

### Apps you might not need
Fedora comes with a lot of apps that aren’t always necessary.
Apps:
- gnome-tour → It’s pretty barebones, doesn’t offer many tips, and is only used once on your first boot.
- gnome-color-manager → Doesn’t even open as a regular app.
- gnome-connections → Can be buggy for some users.
- gnome-contacts → Feels more like a mobile app, not really made for desktop.
- gnome-weather → Doesn’t cover many small cities or villages.
- gnome-abrt → Crash reporting tool, needs setup, and isn’t great for beginners.
- gnome-boxes → Virtualization tool, but only useful if you actually use VMs.
- simple-scan → Document scanner—if you don’t have a scanner, it’s unnecessary.
- snapshot → A very basic camera app, better suited for mobile.

```
# Uninstall
sudo dnf remove gnome-tour gnome-color-manager gnome-connections gnome-contacts gnome-weather gnome-abrt gnome-boxes simple-scan snapshot

# Restore
sudo dnf install gnome-tour gnome-color-manager gnome-connections gnome-contacts gnome-weather gnome-abrt gnome-boxes simple-scan snapshot
```
#
### System services you might not want
If you don’t need these services, you can remove them to keep things lean.
- abrt → It’s an automatic crash reporter. While it’s useful for developers, it’s not really needed for most home users.
```
# Uninstall
sudo dnf remove abrt

# Restore
sudo dnf install abrt
```
> [!NOTE]  
> Removing this also cleans up the "Diagnostics" section in Settings → Privacy.

#
### Small boot speed tweak
This service waits for a full network connection before completing the boot process. If you’re not using something that requires internet right at startup (like a VPN), disabling it can shave a few seconds off your boot time.
```
# Disable
sudo systemctl disable NetworkManager-wait-online.service

# Enable
sudo systemctl enable NetworkManager-wait-online.service
```
#
### Got ideas?
If you spot something else pre-installed that feels unnecessary, or you have better app/extension suggestions, let me know. I'm always happy to update this. Hope this helps make your Fedora feel a bit lighter and more yours!


