# ✅ Checklist Migration Windows 10 → Kali Linux (Dual Boot)

## 1. Préparation Windows
- [ ] Sauvegarder mes fichiers importants (disque externe / cloud).
- [ ] Vérifier mes accès (Git, mails, licences).
- [ ] Nettoyer l’espace disque (fichiers inutiles, corbeille).
- [ ] Défragmenter (si HDD).
- [ ] Réduire la partition Windows avec `diskmgmt.msc` (laisser ≥ 50 Go pour Kali).

---

## 2. Clé USB bootable
- [ ] Télécharger l’ISO officielle depuis [kali.org](https://www.kali.org/get-kali).
- [ ] Vérifier l’empreinte SHA256 de l’ISO.
- [ ] Créer une clé bootable avec **Rufus** (Windows).
- [ ] Tester que la clé est bootable.

---

## 3. Configuration BIOS/UEFI
- [ ] Entrer dans le BIOS (`F2`, `DEL`, `F12`).
- [ ] Vérifier que le **mode UEFI** est activé.
- [ ] Désactiver le **Secure Boot** si nécessaire.
- [ ] Mettre la clé USB en premier dans l’ordre de boot.

---

## 4. Installation de Kali
- [ ] Booter sur la clé → choisir *Install*.
- [ ] Choisir langue, clavier, réseau.
- [ ] Créer un **utilisateur standard** + mot de passe fort.
- [ ] Partitionnement : *Guided – use the largest continuous free space*.
- [ ] Activer le chiffrement **LUKS** si souhaité.
- [ ] Installer le bootloader **GRUB** (il détectera Windows 10).

---

## 5. Sécurisation post-installation
- [ ] Mettre à jour Kali :  
  ```bash
  sudo apt update && sudo apt full-upgrade -y
  ```

* [ ] Installer et activer le firewall UFW :

  ```bash
  sudo apt install ufw -y
  sudo ufw enable
  ```
* [ ] Ajouter mes clés SSH pour Git/GitLab.
* [ ] Installer mes outils (IDE, Docker, Ansible, etc.).

---

## 6. Bonnes pratiques

* [ ] Utiliser mon **utilisateur standard** (éviter root).
* [ ] Faire des **sauvegardes régulières**.
* [ ] Créer des **snapshots système** (si en VM).
* [ ] Ne pas utiliser Kali pour mes usages persos (banque, mails sensibles).

```
