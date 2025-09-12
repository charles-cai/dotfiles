# 🚀 Starship + FiraCode Nerd Font Setup (Ubuntu 22.04)

- Starship: https://starship.rs/guide/
- Nerd Fonts: https://www.nerdfonts.com/font-downloads

## 1. Check Current Font
```bash
# check all the fonts installed
fc-list 
fc-list |sort

gsettings get org.gnome.desktop.interface monospace-font-name
# Example: 'Ubuntu Mono 13'
```
*(Save this to revert later if needed.)*

## 2. Download & Install FiraCode Nerd Font
```bash
wget https://github.com/ryanoasis/nerd-fonts/releases/download/v3.4.0/FiraCode.zip
mkdir -p ~/.local/share/fonts/nerdfonts
unzip FiraCode.zip -d ~/.local/share/fonts/nerdfonts/
fc-cache -fv
```

## 3. Apply the Font
- **GUI method:**  
  Terminal → Preferences → Profiles → Text → enable *Custom Font* → choose **FiraCode Nerd Font**.  

- **CLI method:**  
  ```bash
  gsettings set org.gnome.desktop.interface monospace-font-name 'FiraCode Nerd Font 13'
  ```

## 4. Restart Terminal
Close **all** terminal windows/tabs, then reopen to load the new font.

## 5. Verify Starship Glyphs
```bash
starship explain
```
Check icons (arrows, git symbols, etc.) render correctly.

## 6. Revert if Needed
```bash
gsettings set org.gnome.desktop.interface monospace-font-name 'Ubuntu Mono 13'
rm -rf ~/.local/share/fonts/nerdfonts
fc-cache -fv
```
