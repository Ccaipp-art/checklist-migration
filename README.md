# 🖥️ Migration Windows 10 → Kali Linux (Dual Boot)

Ce projet documente ma tentative de migration **Windows 10 → Kali Linux** en **dual boot**, dans un objectif d’apprentissage en administration systèmes & cybersécurité.  
L’idée est de partager un **guide pratique** que d’autres peuvent suivre ou adapter.  

---

## ✅ Checklist Installation Dual Boot

### 1. Préparation Windows
- [ ] Sauvegarder mes fichiers importants (disque externe / cloud).
- [ ] Vérifier mes accès (Git, mails, licences).
- [ ] Nettoyer l’espace disque (fichiers inutiles, corbeille).
- [ ] Défragmenter (si HDD).
- [ ] Réduire la partition Windows avec `diskmgmt.msc` (laisser ≥ 50 Go pour Kali).

---

### 2. Clé USB bootable
- [ ] Télécharger l’ISO officielle : [kali.org/get-kali](https://www.kali.org/get-kali).
- [ ] Vérifier l’empreinte SHA256 de l’ISO.
- [ ] Créer une clé bootable avec **Rufus** (Windows) :
  - Schéma de partition : GPT (UEFI) ou MBR (Legacy).
  - Format : FAT32.
- [ ] Tester que la clé est bootable.

---

### 3. Configuration BIOS/UEFI
- [ ] Redémarrer → entrer dans le BIOS (`F2`, `DEL`, `F12`).
- [ ] Vérifier que le **mode UEFI** est activé.
- [ ] Désactiver le **Secure Boot** si nécessaire.
- [ ] Mettre la clé USB en **1er dans l’ordre de boot**.

---

### 4. Installation de Kali
- [ ] Booter sur la clé → choisir *Install*.
- [ ] Choisir langue, clavier, réseau.
- [ ] Créer un **utilisateur standard** + mot de passe fort.
- [ ] Partitionnement : *Guided – use the largest continuous free space*.
- [ ] Activer le chiffrement LUKS si souhaité.
- [ ] Installer le bootloader **GRUB** (il détectera Windows 10).

---

### 5. Sécurisation post-installation
- [ ] Mettre à jour Kali :
  ```bash
  sudo apt update && sudo apt full-upgrade -y
````

* [ ] Installer et activer le firewall UFW :

  ```bash
  sudo apt install ufw -y
  sudo ufw enable
  ```
* [ ] Ajouter mes clés SSH pour Git/GitLab.
* [ ] Installer mes outils (IDE, Docker, Ansible, etc.).

---

### 6. Bonnes pratiques

* [ ] Utiliser mon **utilisateur standard** (éviter root).
* [ ] Faire des **sauvegardes régulières**.
* [ ] Créer des **snapshots système** (si en VM).
* [ ] Ne pas utiliser Kali pour mes usages persos (banque, mails sensibles).

---

## 📌 Objectif

Ce projet est lié à mon parcours en **cybersécurité et administration systèmes** dans le cadre de ma future alternance d’**Administrateur Infrastructures Sécurisées**.
Il me permet de documenter mes apprentissages et de partager une méthode reproductible.

---

## 📎 Ressources utiles

* [Documentation officielle Kali Linux](https://www.kali.org/docs/)
* [Créer une clé bootable avec Rufus](https://rufus.ie/)
* [Guide dual boot Windows/Linux (Debian)](https://wiki.debian.org/fr/DualBoot)

---

👤 Auteur : [Théo FRANCOIS](https://www.linkedin.com/in/tfs-ccaipp)

```

