# Tidy My Fedora 🧽

Based on the [Fedora Noble Guide](https://github.com/wz790/Fedora-Noble-Setup), with targeted modifications.

This guide helps you clean up a fresh Fedora installation by removing optional packages and providing recommendations for practical applications, GNOME extensions, and system tweaks to make your desktop setup easier to manage.

### 🔄 Reversible Changes
This guide helps you clean up a fresh Fedora installation. Every item includes both a remove command and a restore command, so you can safely undo any changes at any time.

- **Uninstall** command – remove it from your system.
- **Restore** command – reinstall it anytime if needed.

> 📃 Note<br> 
Some packages may have dependencies or optional weak dependencies. When using the uninstall or restore commands, DNF may automatically remove or install additional packages to satisfy these dependencies. Always check the command output before confirming. If you want to prevent DNF from automatically removing dependent packages, you can optionally add the --noautoremove flag at the end of your uninstall command:
```
sudo dnf remove <package> --noautoremove
```

<p align=center>  ───────── ౨ৎ ───────── </p>

### 🧹 Remove unnecessary Add-ons
These add-ons are optional. Remove any you don’t need.

- **ibus-m17n** – Support for multiple multilingual input methods
- **ibus-typing-booster** – Predictive typing input method
- **ibus-hangul** – Korean input support
- **ibus-libpinyin** – Chinese Pinyin input method
- **ibus-anthy** – Japanese input support

```
# Uninstall
sudo dnf remove ibus-m17n ibus-typing-booster ibus-hangul ibus-libpinyin ibus-anthy

# Restore
sudo dnf install ibus-m17n ibus-typing-booster ibus-hangul ibus-libpinyin ibus-anthy
```

> 📃 Note<br>
These input source add-ons can be found in Software ➞ Explore ➞ very bottom ➞ Input Sources

<p align=center>  ───────── ౨ৎ ───────── </p>

### 🚫 Apps You Might Not Need
These apps are optional and can be removed if you don’t plan to use them.

- **gnome-tour** – Not very useful after first boot
- **gnome-color-manager** – Cannot be launched as a standalone app
- **gnome-connections** – Users report it crashes often
- **gnome-contacts** – Does not show all cities
- **gnome-weather** – Japanese input support
- **gnome-abrt** - Requires an API key; not very useful for new users

```
# Uninstall
sudo dnf remove gnome-tour gnome-color-manager gnome-connections gnome-contacts gnome-weather gnome-abrt

# Restore
sudo dnf install gnome-tour gnome-color-manager gnome-connections gnome-contacts gnome-weather gnome-abrt
```

<p align=center>  ───────── ౨ৎ ───────── </p>

### 🔴 Optional System Services
Disable or remove these services if not required for your setup.

- **abrt** - Automatic Bug Reporting Tool; collects and reports application crashes. Not essential for new users.

```
# Uninstall
sudo dnf remove abrt

# Restore
sudo dnf install abrt
```

> 📃 Note<br>
Removing this package also removes the Diagnostics menu under Settings ➞ Privacy & Security.

<p align=center>  ───────── ౨ৎ ───────── </p>

### ⚡ Optional Boot Tweaks
Disable or adjust these boot services if you don’t need them.

- **NetworkManager-wait-online.service** - Delays boot until a network connection is fully established.

```
# Disable
sudo systemctl disable NetworkManager-wait-online.service

# Enable
sudo systemctl enable NetworkManager-wait-online.service
```
> 📃 Note<br>
Disabling NetworkManager-wait-online.service can speed up boot slightly, but may impact services that need a network connection at startup (e.g., VPNs or cloud sync).

<p align=center>  ───────── ౨ৎ ───────── </p>

### 🚀 Recommended Applications
Here are some recommended applications that can enhance your Fedora experience. These apps are useful, easy to install, and can help improve your workflow.

- 🖊️ [**Gradia**](https://flathub.org/en/apps/be.alexandervanhee.gradia) – Annotate your screenshots
- 📦 [**Warehouse**](https://flathub.org/en/apps/io.github.flattool.Warehouse) – Manage all things Flatpak 
- 🔐 [**Flatseal**](https://flathub.org/en/apps/com.github.tchx84.Flatseal) – Control Flatpak permissions
- 📊 [**Resources**](https://flathub.org/en/apps/net.nokyan.Resources) – Monitor system resources
- ...

<p align=center>  ───────── ౨ৎ ───────── </p>

### 🧩 GNOME Extensions
To get started with GNOME extensions, install [Extension Manager](https://flathub.org/en/apps/com.mattjakeman.ExtensionManager). It helps you easily find, install, and manage extensions.

- [Foresight](https://extensions.gnome.org/extension/7901/foresight/) – Automatically opens the Activities view when no windows are open in the current workspace.
- TBA
- TBA
- ...

> 📃 Note<br>
Install GNOME extensions one at a time and monitor their behavior. Conflicting extensions may cause desktop instability, and having too many can slow down your system.

<p align=center>  ───────── ౨ৎ ───────── </p>

### 🤝 Suggestions and Contributions
Have recommendations or notice issues? Open an issue! If you know of pre-installed apps, add-ons, or services that can be safely removed or disabled, please share - they help improve this guide.

<p align=center>  ───────── ౨ৎ ───────── </p>
