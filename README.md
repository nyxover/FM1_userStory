# FM1_userStory
UserStory FM1 of nyxover

Félicitations pour ton **M-VAVE FM-1** ! 

Le détail que tu mentionnes (**« écrit M-wave en bas de l'écran »**) est **crucial** : cela indique que tu possèdes une révision matérielle plus récente (souvent équipée de la nouvelle puce mémoire flash `UC25HQ80`, JEDEC ID `0xB36014`). Il y a quelques mois, flasher certains anciens firmwares sur cette version pouvait poser des problèmes de sauvegarde ou de soft-brick, mais la communauté a mis à jour les firmwares pour supporter cette révision.

Voici le guide complet pas-à-pas (To-Do List) pour transformer ce petit synthé FM à 25 € en véritable bête de scène (Groovebox 303/808/909, synthétiseur DX7, machine ambient, etc.).

---

## 📋 Checklist & Tuto Pas-à-Pas

### Étape 1 : Pré-requis et matériel
- [ ] **Un ordinateur** avec un navigateur moderne (Chrome, Edge ou Opera recommandés pour le support WebMIDI / WebUSB).
- [ ] **Un câble USB-C vers USB-A ou USB-C de qualité** (assure-toi qu'il gère bien le transfert de données, pas un simple câble de charge).
- [ ] Connecte ton M-VAVE FM-1 allumé à ton PC en USB.

---

### Étape 2 : Le WebFlasher (La méthode la plus simple)
Pas besoin d'installer Python ou de compiler du code : la communauté a mis en place des outils de flash direct via le navigateur en SysEx/MIDI.

- [ ] Rends-toi sur le hub communautaire : [fm1-custom-fw (aroum)](https://github.com/aroum/fm1-custom-fw) ou sur **The Firmware Hub** dédié au FM-1.
- [ ] Vérifie que ton périphérique MIDI est bien détecté dans le navigateur sous le nom **M-VAVE FM-1** (ou similaire).
- [ ] **Sauvegarde (Backup) :** Si l'outil le propose, télécharge toujours une copie de sauvegarde de la ROM d'origine / patches pour pouvoir revenir en arrière en cas de besoin.

---

### Étape 3 : Choisir ton Custom Firmware (CFW)
C'est là que le « hack » prend tout son sens : le FM-1 utilise un SoC JieLi capable de faire tourner des firmwares complètement différents.

Voici les plus populaires :

1. **sloop-fm1 (par isod89) :**
   - *Ce que c'est :* Une véritable **Groovebox autonome en direct**.
   - *Fonctions :* Séquenceur complet, bouclage temps réel, plusieurs pistes.
2. **fm1-x0x (par charlesvestal) :**
   - *Ce que c'est :* Inspiré des légendaires machines Roland (fork de *Felucca*).
   - *Fonctions :* Émulation boîte à rythmes 808/909, deux synthés TB-303 (acid bassline) avec générateur TB-3PO, générateur de breakbeats et Song Mode.
3. **Felucca (par hugelton) / Hortator :**
   - *Ce que c'est :* Le premier gros custom firmware modulaire pour le FM-1.
   - *Fonctions :* Synthèse granulaire, drones, polyphonie améliorée, arpégiateurs avancés.
4. **AMB-1 / fm1-amb (par charlesvestal) :**
   - *Ce que c'est :* Machine générative ambient inspirée de *Music for Airports* de Brian Eno. Idéal pour des nappes génératives infinies.

> ⚠️ **Attention révision M-wave :** Assure-toi de toujours télécharger la **dernière version (Latest Release)** du firmware choisi (ex. versions sorties après octobre 2026), qui intègrent le support des écrans et puces flash récentes pour éviter tout bug de sauvegarde.

---

### Étape 4 : Flasher le firmware
- [ ] Sélectionne le fichier `.bin` ou `.syx` du firmware choisi dans l'interface WebFlasher.
- [ ] Lance le flash (Update/Flash).
- [ ] **NE DÉBRANCHE SURTOUT PAS** le câble pendant l'envoi des données. L'écran du FM-1 ou les LEDs vont clignoter.
- [ ] Une fois terminé (100%), éteins puis rallume le FM-1.

---

### Étape 5 : Bonus – Les Patches DX7 (Sans changer de firmware)
Si tu souhaites garder le moteur de synthèse FM d'origine mais multiplier ses sons par 1 000 :
- [ ] Utilise le projet **`fm1-dx7-patch-importer`** (par benny-sparra).
- [ ] Il te permet de convertir et d'importer directement des fichiers de banques SysEx `.syx` du légendaire **Yamaha DX7** dans la mémoire de ton FM-1.
- [ ] Il existe des dizaines de milliers de patches DX7 gratuits disponibles en ligne (basses FM percutantes, e-pianos 80s, cloches, etc.).

---

### En cas de pépin (Secours / Unbrick)
Si jamais l'appareil refuse de démarrer ou si l'écran reste noir :
- Pas de panique : le bootloader matériel JieLi est généralement difficile à détruire.
- En maintenant une combinaison de touches (Power + Bouton spécifique selon la documentation) à l'insertion de l'USB, l'appareil se remet en mode bootloader de secours (voir le *Rescue Guide* sur le hub `aroum/fm1-custom-fw`).
