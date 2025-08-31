# Installation des IDE JetBrains sans droits administrateur (Linux)

Ce guide explique comment installer et utiliser **PhpStorm, WebStorm, PyCharm et IntelliJ IDEA** depuis les archives `.tar.gz`, sans nécessiter les droits administrateur. D'autres logiciels marchent aussi (ex: Thunderbird)
L’intégration au menu des applications est réalisée via des fichiers `.desktop` stockés dans `~/.local/share/applications/`.

---

## 📦 Étape 1 — Télécharger les archives `.tar.gz`

Rendez-vous sur la page officielle des produits JetBrains :  
👉 https://www.jetbrains.com/products/

Exemple (PyCharm) :  
```bash
wget https://download.jetbrains.com/python/pycharm-community-2025.1.tar.gz -P ~/Downloads
```

Faites de même pour :
- PhpStorm  
- WebStorm  
- IntelliJ IDEA
- Clion

---

## 📂 Étape 2 — Extraire les archives

Décompressez chaque archive dans un dossier de votre choix (par ex. `~/jetbrains`) :

```bash
mkdir -p ~/jetbrains
tar -xvzf ~/Downloads/pycharm-*.tar.gz -C ~/jetbrains
tar -xvzf ~/Downloads/phpstorm-*.tar.gz -C ~/jetbrains
tar -xvzf ~/Downloads/webstorm-*.tar.gz -C ~/jetbrains
tar -xvzf ~/Downloads/ideaIC-*.tar.gz -C ~/jetbrains
```

Chaque IDE sera dans son dossier respectif (`pycharm-2025.x.x/`, `phpstorm-2025.x.x/`, etc.).

---

## ▶️ Étape 3 — Lancer un IDE

Exemple pour **PyCharm** :
```bash
~/jetbrains/pycharm-2025.1/bin/pycharm.sh &
```

---

## 🖥 Étape 4 — Créer les lanceurs `.desktop`

Les fichiers `.desktop` permettent d’ajouter les IDE au menu des applications.  
Ils doivent être placés dans `~/.local/share/applications/`.

Créez le dossier si nécessaire :
```bash
mkdir -p ~/.local/share/applications
```

### Exemple : `pycharm.desktop`

Créez le fichier `~/.local/share/applications/pycharm.desktop` :

```ini
[Desktop Entry]
Version=1.0
Type=Application
Name=PyCharm
Exec=/home/$USER/goinfre/jetbrains/pycharm-2025.1/bin/pycharm.sh
Icon=/home/$USER/goinfre/jetbrains/pycharm-2025.1/bin/pycharm.png
Comment=Python IDE by JetBrains
Categories=Development;IDE;
Terminal=false
```

### Exemple : `phpstorm.desktop`

```ini
[Desktop Entry]
Version=1.0
Type=Application
Name=PhpStorm
Exec=/home/$USER/goinfre/jetbrains/phpstorm-2025.1/bin/phpstorm.sh
Icon=/home/$USER/goinfre/jetbrains/phpstorm-2025.1/bin/phpstorm.png
Comment=PHP IDE by JetBrains
Categories=Development;IDE;
Terminal=false
```

### Exemple : `webstorm.desktop`

```ini
[Desktop Entry]
Version=1.0
Type=Application
Name=WebStorm
Exec=/home/$USER/goinfre/jetbrains/webstorm-2025.1/bin/webstorm.sh
Icon=/home/$USER/goinfre/jetbrains/webstorm-2025.1/bin/webstorm.png
Comment=JavaScript IDE by JetBrains
Categories=Development;IDE;
Terminal=false
```

### Exemple : `intellij.desktop`

```ini
[Desktop Entry]
Version=1.0
Type=Application
Name=IntelliJ IDEA
Exec=/home/$USER/goinfre/jetbrains/ideaIC-2025.1/bin/idea.sh
Icon=/home/$USER/goinfre/jetbrains/ideaIC-2025.1/bin/idea.png
Comment=Java IDE by JetBrains
Categories=Development;IDE;
Terminal=false
```

### Exemple : `clion.desktop`

```ini
[Desktop Entry]
Version=1.0
Type=Application
Name=CLion
Exec=/home/$USER/goinfre/jetbrains/clion-2025.1/bin/clion.sh
Icon=/home/$USER/goinfre/jetbrains/clion-2025.1/bin/clion.png
Comment=C/C++ IDE by JetBrains
Categories=Development;IDE;
Terminal=false
```

### Exemple : `thunderbird.desktop`

```ini
[Desktop Entry]
Version=1.0
Type=Application
Name=Thunderbird
Exec=/home/$USER/goinfre/thunderbird/thunderbird
Icon=/home/$USER/goinfre/thunderbird/chrome/icons/default/default128.png
Comment=Client de messagerie
Categories=Network;Email;
Terminal=false
```

---

## 🔄 Étape 5 — Rafraîchir la base des applications

Exécutez :
```bash
update-desktop-database ~/.local/share/applications
```

Si la commande n’est pas disponible, il suffit de se déconnecter/reconnecter pour voir apparaître les applications dans le menu.

---

## ✅ Résultat

Vous pouvez désormais lancer **PhpStorm, WebStorm, PyCharm, IntelliJ IDEA** directement depuis le menu des applications, sans droits root. 🚀
