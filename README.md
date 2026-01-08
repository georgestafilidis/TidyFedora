# Tidy My Fedora 🧽

This is based on the [**Fedora Noble Guide**](https://github.com/wz790/Fedora-Noble-Setup), but I've tweaked it a bit.

The goal here is to help you remove stuff you probably don't need on a new Fedora setup. I'll also suggest some handy apps, GNOME extensions, and small tweaks to make things feel cleaner and easier to use.

### 🔄 Everything is reversible
For every change, I'll give you the command to undo it. So if you remove something and later think "wait, I kinda want that back," just run the restore command.

> When removing packages, DNF might want to pull out other stuff that depends on them. Always read what it's planning to do before you hit yes. If you want to stop it from auto-removing extras, add --noautoremove to the end of the remove command.

```
sudo dnf remove <package> --noautoremove
```

<p align=center>  ───────── ౨ৎ ───────── </p>

### 🧹 Get rid of extra input methods
These are for typing in different languages. If you only use English (or whatever your main language is), you can safely ditch them.
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

> You can find these in the Software app under Input Sources at the very bottom.

<p align=center>  ───────── ౨ৎ ───────── </p>

### 🚫 Apps you might not need
These come pre-installed but aren't super useful for everyone.

- gnome-tour → just the welcome screen you see once
- gnome-color-manager → doesn't even open as a normal app
- gnome-connections → kinda buggy for a lot of people
- gnome-contacts → doesnt really fit the desktop more like it was made for phones
- gnome-weather → simple weather app (there are better ones)
- gnome-abrt → crash reporting tool that needs setup and isn't great for beginners

```
# Uninstall
sudo dnf remove gnome-tour gnome-color-manager gnome-connections gnome-contacts gnome-weather gnome-abrt

# Restore
sudo dnf install gnome-tour gnome-color-manager gnome-connections gnome-contacts gnome-weather gnome-abrt
```

<p align=center>  ───────── ౨ৎ ───────── </p>

### 🔴 System services you might not want
Disable or remove these services if not required for your setup.

- abrt → automatic crash reporter. Nice idea, but not really needed for most home users.

```
# Uninstall
sudo dnf remove abrt

# Restore
sudo dnf install abrt
```

> Removing this also cleans up the "Diagnostics" section in Settings → Privacy.

<p align=center>  ───────── ౨ৎ ───────── </p>

### ⚡ Small boot speed tweak
This one service waits for full network connection before finishing boot. If you're not using something that needs internet right at startup (like a VPN), disabling it shaves a few seconds off boot time.

```
# Disable
sudo systemctl disable NetworkManager-wait-online.service

# Enable
sudo systemctl enable NetworkManager-wait-online.service
```


<p align=center>  ───────── ౨ৎ ───────── </p>

### 🚀 Some Flatpak apps I actually use and recommend
Fedora has Flatpak ready to go out of the box. These are sandboxed, update easily, and don't mess with your system packages.

Must-haves:
- 🔐 [**Flatseal**](https://flathub.org/en/apps/com.github.tchx84.Flatseal) (⭐) – Easily manage and review Flatpak permissions
- 🧩 [**Extension Manager**](https://flathub.org/en/apps/com.mattjakeman.ExtensionManager) (⭐) - Easily find, install, and manage GNOME extensions

Nice extras:
- 📦 [**Warehouse**](https://flathub.org/en/apps/io.github.flattool.Warehouse) – Manage all things Flatpak 
- 🖊️ [**Gradia**](https://flathub.org/en/apps/be.alexandervanhee.gradia) – Annotate your screenshots
- 📊 [**Resources**](https://flathub.org/en/apps/net.nokyan.Resources) – Monitor system resources
- ...

<p align=center>  ───────── ౨ৎ ───────── </p>

### 🧩 GNOME extensions worth trying
First, grab Extension Manager from above - it makes life way easier.

Some solid ones:
- [**Foresight**](https://extensions.gnome.org/extension/7901/foresight/) – Automatically opens the Activities view when no windows are open in the current workspace
- [**Static Workspace Background**](https://extensions.gnome.org/extension/8505/static-workspace-background/) - Keep a static background while changing workspaces in GNOME
- [**Essential Tweaks**](https://extensions.gnome.org/extension/8928/essential-tweaks/) - Tweak annoying defaults and enable quality of life features
- [**Blur my Shell**](https://extensions.gnome.org/extension/3193/blur-my-shell/) - Adds a blur look to different parts of the GNOME Shell, including the top panel, dash and overview.
- ...

Install them one by one. Too many extensions at once can make things sluggish or buggy.

<p align=center>  ───────── ౨ৎ ───────── </p>

### 🤝 Got ideas?
If you spot something else pre-installed that feels unnecessary, or you have better app/extension suggestions, let me know. I'm always happy to update this. Hope this helps make your Fedora feel a bit lighter and more yours!
