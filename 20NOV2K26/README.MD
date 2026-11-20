Ces deux liens sont de véritables pépites ! Tu es tombé sur les deux projets les plus impressionnants de la scène FM-1 :

1. **SHRUB (shrub.audio)** : C'est une prouesse folle — ils ont porté une version allégée du moteur wavetable de **Serum (Xfer)** sur cette puce à 25 € ! On passe d'un synthé FM classique à un synthétiseur wavetable complet avec filtres Serum 2, modulations LFO, racks d'effets (distorsion, chorus, reverb...) et éditeur web.
2. **fm1-emu (joakimeriksson.github.io)** : Un émulateur complet en WebAssembly capable de faire tourner plus de 200 firmwares directement dans ton navigateur. C'est le bac à sable idéal pour tout tester **sans toucher à ton FM-1**.

Voici la **To-Do List optimale** pour profiter de tout cela en toute sécurité avec ton modèle (révision avec mention *M-wave* en bas de l'écran).

---

## 🧭 Le Workflow Idéal (Étape par étape)

```
[ Étape 1 : Tester sur l'Émulateur ]
                ↓
[ Étape 2 : Sauvegarder la ROM Stock ]
                ↓
[ Étape 3 : Flasher SHRUB en 1 clic via WebMIDI ]
                ↓
[ Étape 4 : Designer tes sons avec l'Éditeur Web ]
```

---

### Étape 1 : Le bac à sable (fm1-emu)
Avant d'envoyer quoi que ce soit sur ton appareil physique, utilise l'émulateur pour découvrir les firmwares :
- [ ] Ouvre **[joakimeriksson.github.io/fm1-emu](https://joakimeriksson.github.io/fm1-emu/)** sur Chrome ou Edge.
- [ ] Tu peux tester plus de **200 firmwares** (Felucca, X0X, SLOOP, SHRUB...) directement au clavier d'ordinateur ou avec un clavier MIDI branché au PC.
- [ ] *Astuce pour ta révision :* Dans l'émulateur, le paramètre `?chip=uc25hq80` simule précisément la nouvelle puce de mémoire flash présente sur les FM-1 avec la mention « M-wave » en bas de l'écran.

---

### Étape 2 : Préparer le FM-1 pour le flash de SHRUB
Pour installer SHRUB, pas besoin de logiciel lourd : tout se fait via WebMIDI dans ton navigateur.

- [ ] **Navigateur recommandé :** Google Chrome ou Microsoft Edge (sur PC ou Mac). Safari et Firefox ne gèrent pas le WebMIDI de la même façon.
- [ ] Ferme tous les logiciels audio (DAW comme Ableton, FL Studio, Reaper) et l'utilitaire M-Upgrade officiel : sur Windows, un seul programme peut ouvrir le port MIDI à la fois.
- [ ] Connecte ton M-VAVE FM-1 à l'ordinateur avec un bon câble USB-C (données + alimentation) et allume-le.
- [ ] *(Optionnel mais recommandé)* Télécharge et garde au chaud le firmware stock d'origine au cas où tu voudrais revenir au son d'usine (version [V15 / V16 .fwsc](https://joakimeriksson.github.io/fm1-emu/#stock)).

---

### Étape 3 : Flasher SHRUB sur le FM-1
- [ ] Rends-toi sur la page d'installation : **[shrub.audio/editor/install](https://shrub.audio/editor/install)**.
- [ ] Clique sur **« Use the SHRUB on this site »** (ou sélectionne le package `.fwsc`).
- [ ] Clique sur **Install**.
- [ ] Autorise le navigateur à accéder à tes périphériques MIDI lorsqu'une pop-up te le demande.
- [ ] **Patience :** Le flash prend environ 2 minutes. L'écran de ton FM-1 va afficher `SHRUB UPDATE`.
  > ⚠️ **Ne débranche surtout pas le câble** pendant le transfert !
- [ ] Une fois terminé, le FM-1 redémarre sous SHRUB.

---

### Étape 4 : Prendre en main SHRUB
Une fois flashé, le FM-1 ne ressemble plus du tout à sa version d'usine :
- [ ] **L'éditeur temps réel :** Ouvre **[shrub.audio/editor/](https://shrub.audio/editor/)** tout en laissant ton FM-1 branché en USB. L'éditeur contrôle et envoie tes tables d'ondes, filtres, enveloppes et effets directement dans la machine en live.
- [ ] **Le guide :** Consulte le **[Operation Guide de Shrub](https://shrub.audio/guide/)** pour comprendre comment naviguer dans les menus avec les touches et potards du FM-1 (accès aux 2 oscillateurs wavetables, motion sequencer, matrice de modulation).

---

### 🛟 Filet de sécurité : Que faire si ça coince ?
Si le flash s'interrompt ou si tu veux changer de firmware :
1. **Mode Recovery USB matériel :** Avec le câble USB branché, **maintiens enfoncées les touches `OCT−` et `OCT+`** tout en allumant l'appareil. Cela force le bootloader de secours de la puce JieLi.
2. Pour revenir au firmware FM d'origine (Dexed / DX7), il te suffit de réinjecter le fichier officiel `FM-1.fwsc` via l'utilitaire M-VAVE ou le WebFlasher.
