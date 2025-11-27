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
<p align="center">Have recommendations or notice issues? Open an issue! If you know of pre-installed apps, add-ons, or services that can be safely removed or disabled, please share—they help improve this guide.</p>

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

<table>
<tr>
<td><img src="https://github.com/user-attachments/assets/2683131b-bf07-42c2-91fe-b1cb55b1eaee" width="128" height="128" alt="Gradia"></td>
<td>
<strong>Gradia</strong> – annotate your screenshots. Helps prepare screenshots quickly for sharing with friends, colleagues, or for professional use.<br>
<a href="https://flathub.org/en/apps/be.alexandervanhee.gradia" target="_blank">View on Flathub</a>
</td>
</tr>
</table>

<table>
<tr>
<td><img width="128" height="128" alt="Warehouse" src="https://github.com/user-attachments/assets/ad7ea02d-b031-4aec-8c23-81ccf143fd9a"></td>
<td>
<strong>Warehouse</strong> – manage all things Flatpak. Provides a simple UI to control complex Flatpak options without using the command line.<br>
<a href="https://flathub.org/en/apps/io.github.flattool.Warehouse" target="_blank">View on Flathub</a>
</td>
</tr>
</table>

<table>
<tr>
<td><img width="128" height="128" alt="Flatseal" src="https://github.com/user-attachments/assets/7db809f7-6173-40dc-8897-100ab53c7ae3"></td>
<td>
<strong>Flatseal</strong> – Manage Flatpak permissions. A graphical utility to review and modify permissions of your Flatpak applications.<br>
<a href="https://flathub.org/en/apps/com.github.tchx84.Flatseal" target="_blank">View on Flathub</a>
</td>
</tr>
</table>

---

<h3 align="center">🧩 GNOME Extensions</h3>
<p align="center">This section will list useful GNOME extensions that enhance your desktop experience. More extensions will be added soon.</p>

Extension 1 – Description (coming soon)

Extension 2 – Description (coming soon)

Extension 3 – Description (coming soon)


