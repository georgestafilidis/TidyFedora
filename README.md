```
    ███      ▄█  ████████▄  ▄██   ▄           ▄████████    ▄████████ ████████▄   ▄██████▄     ▄████████    ▄████████ 
▀█████████▄ ███  ███   ▀███ ███   ██▄        ███    ███   ███    ███ ███   ▀███ ███    ███   ███    ███   ███    ███ 
   ▀███▀▀██ ███▌ ███    ███ ███▄▄▄███        ███    █▀    ███    █▀  ███    ███ ███    ███   ███    ███   ███    ███ 
    ███   ▀ ███▌ ███    ███ ▀▀▀▀▀▀███       ▄███▄▄▄      ▄███▄▄▄     ███    ███ ███    ███  ▄███▄▄▄▄██▀   ███    ███ 
    ███     ███▌ ███    ███ ▄██   ███      ▀▀███▀▀▀     ▀▀███▀▀▀     ███    ███ ███    ███ ▀▀███▀▀▀▀▀   ▀███████████ 
    ███     ███  ███    ███ ███   ███        ███          ███    █▄  ███    ███ ███    ███ ▀███████████   ███    ███ 
    ███     ███  ███   ▄███ ███   ███        ███          ███    ███ ███   ▄███ ███    ███   ███    ███   ███    ███ 
   ▄████▀   █▀   ████████▀   ▀█████▀         ███          ██████████ ████████▀   ▀██████▀    ███    ███   ███    █▀  
                                                                                             ███    ███              
```

Based on the [Fedora Noble Guide](https://github.com/wz790/Fedora-Noble-Setup), with targeted modifications.

This guide removes packages typically unnecessary on a clean Fedora installation and provides recommendations for practical applications and GNOME extensions to optimize a default setup.


<h3 align="center">🤝 Suggestions and Contributions</h3>
<p align="center">Have recommendations or notice issues? Open an issue! If you know of pre-installed apps, add-ons, or services that can be safely removed or disabled, please share - they help improve this guide.</p>

---

<h3 align="center">🧹 Remove unnecessary Add-ons</h3>
<p align="center">These add-ons can be removed <strong>if not needed</strong> to reduce bloat and improve system performance.</p>
<br>

| Add-on Name          | Reason for Removal                        |
|----------------------|------------------------------------------|
| **ibus-m17n**        | Support for multiple multilingual input methods |
| **ibus-typing-booster** | Predictive typing input method           |
| **ibus-hangul**      | Korean input support                     |
| **ibus-libpinyin**   | Chinese Pinyin input method              |
| **ibus-anthy**       | Japanese input support                   |
<br>

Uninstall command:
```
sudo dnf remove ibus-m17n ibus-typing-booster ibus-hangul ibus-libpinyin ibus-anthy
```

Restore command:
```
sudo dnf install ibus-m17n ibus-typing-booster ibus-hangul ibus-libpinyin ibus-anthy
```

> Note: These input source add-ons can be found in Software ➞ Explore ➞ very bottom ➞ Input Sources
<br>

---

<h3 align="center">🚫 Apps You Might Not Need</h3>
<p align="center">Remove these apps <strong>if not needed</strong> to streamline your system and avoid unnecessary features.</p>
<br>

| App Name            | Reason for Removal                           |
|---------------------|---------------------------------------------|
| **gnome-tour**      | Not very useful after first boot            |
| **gnome-color-manager** | Cannot be launched as a standalone app     |
| **gnome-connections** | Users report it crashes often              |
| **gnome-contacts**  | Generally unnecessary on desktop            |
| **gnome-weather**   | Does not show all cities                    |
| **gnome-abrt**      | Requires an API key; not very useful for new users |
<br>

Uninstall command:
```
sudo dnf remove gnome-tour gnome-color-manager gnome-connections gnome-contacts gnome-weather gnome-abrt
```

Restore command:
```
sudo dnf install gnome-tour gnome-color-manager gnome-connections gnome-contacts gnome-weather gnome-abrt
```

---

<h3 align="center">🛑 Optional System Services</h3>
<p align="center">These background services can be disabled or removed <strong>if not needed</strong> for your system's usage.</p>

| Service Name                        | Reason for Removal                                                       |
|-------------------------------------|--------------------------------------------------------------------------|
| **abrt**                            | Automatic Bug Reporting Tool; collects and reports application crashes. Not essential for new users. <br> Note: Removing this package also removes the Diagnostics menu under Settings ➞ Privacy & Security. |
<br>

Uninstall command:
```
sudo dnf remove abrt
```
Restore command:
```
sudo dnf install abrt
```

---

<h3 align="center">⚡ Optional Boot Tweaks</h3>
<p align="center">Disable or tweak these boot-related services <strong>if not needed</strong> for faster startup times or specific requirements.</p>

| Service Name                        | Reason for Removal                                                       |
|-------------------------------------|--------------------------------------------------------------------------|
| **NetworkManager-wait-online.service** | Delays boot until a network connection is fully established. Disabling this speeds up boot but may affect services that require the network at startup. |
<br>

Disable command:
```
sudo systemctl disable NetworkManager-wait-online.service
```

Enable command:
```
sudo systemctl enable NetworkManager-wait-online.service
```

---

<h3 align="center">🚀 Recommended Applications</h3>
<p align="center">Here are some recommended applications that can enhance your Fedora experience. These apps are useful, easy to install, and can help improve your workflow.</p>

![Gradia Logo](https://github.com/georgestafilidis/minimal-fedora-setup/blob/faac4f6918cdabef2f8cfbde75f807ff0944133e/assets/Gradia.png?raw=true)

| [**Gradia**](https://flathub.org/en/apps/be.alexandervanhee.gradia)       |
|---------------------------------------------------------------------------|
| Annotate your screenshots.                                                 |


![Warehouse Logo](https://github.com/georgestafilidis/minimal-fedora-setup/blob/faac4f6918cdabef2f8cfbde75f807ff0944133e/assets/Warehouse.png?raw=true)

| [**Warehouse**](https://flathub.org/en/apps/io.github.flattool.Warehouse) |
|---------------------------------------------------------------------------|
| Manage all things Flatpak.                                                 |


![Flatseal Logo](https://github.com/georgestafilidis/minimal-fedora-setup/blob/faac4f6918cdabef2f8cfbde75f807ff0944133e/assets/Flatseal.png?raw=true)

| [**Flatseal**](https://flathub.org/en/apps/com.github.tchx84.Flatseal)     |
|---------------------------------------------------------------------------|
| Manage Flatpak permissions.                                                |


![Resources Logo](https://github.com/georgestafilidis/TidyFedora/blob/858c51cd39cfe49c8052873aec28e17db7b5dc3c/assets/Resources.png?raw=true)

| [**Resources**](https://flathub.org/en/apps/net.nokyan.Resources)          |
|---------------------------------------------------------------------------|
| Keep an eye on system resources.                                           |


<h3 align="center">🧩 GNOME Extensions</h3>
<p align="center">This section will list useful GNOME extensions that enhance your desktop experience. More extensions will be added soon.</p>

[Foresight](https://extensions.gnome.org/extension/7901/foresight/) – Automagically opens the activities view when workspace is empty. It uses callbacks to monitor windows and workspaces (instead of actively checking on them on certain time intervals), which makes it very efficient and responsive.

Extension 2 – Description (coming soon)

Extension 3 – Description (coming soon)


