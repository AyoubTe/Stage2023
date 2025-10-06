# 🧩 Automatisation de la Gestion d’Infrastructure

## 🎓 Projet de Stage d’Initiation Professionnelle
**École :** École Hassania des Travaux Publics (EHTP)  
**Entreprise d’accueil :** IT24.MA  
**Année universitaire :** 2022/2023  
**Réalisé par :** Ayoub SAMI  
**Encadré par :** Ismail AIT ZAID  

---

## 🧠 Résumé du Projet

Ce projet a pour objectif **d’automatiser la gestion d’infrastructure informatique** (serveurs, bases de données, machines virtuelles) au sein de l’entreprise **IT24**.  
L’automatisation permet de simplifier les opérations d’administration, d’améliorer la sécurité et d’optimiser les ressources.

L’outil principal utilisé est **Ansible**, qui permet de gérer les configurations et de déployer des applications de manière automatisée via une connexion **SSH sécurisée (OpenSSH)**.

Une machine **Master** (sous RHEL 7.9) orchestre la gestion de l’ensemble de l’infrastructure virtuelle créée sur **VirtualBox**.

---

## 🏢 Présentation de l’Entreprise IT24

**IT24.MA** est une société marocaine spécialisée dans :  
- 🔗 **Réseaux informatiques** (Intranet, IP/MPLS, WiFi, ToIP, visioconférence)  
- 🔐 **Cybersécurité** (NOC, SOC, sécurité réseau)  
- 📹 **Sécurité électronique** (vidéosurveillance, contrôle d’accès, biométrie)  

**Services principaux :**
- Maintenance et support informatique  
- Installation et administration de serveurs  
- Sauvegarde et récupération de données  
- Développement web et gestion commerciale  

---

## ⚙️ Architecture de la Solution

L’infrastructure repose sur une **machine Master** et plusieurs **nœuds (workers)** :

| Machine | Adresse IP | Rôle |
|----------|-------------|------|
| Master | 192.168.43.130 | Nœud maître – contrôle Ansible |
| Worker 1 | 192.168.43.132 | Serveur web |
| Worker 2 | 192.168.43.133 | Serveur de production |
| Worker 3 | 192.168.43.134 | Base de données |
| Web Server 2 | 192.168.43.135 | Serveur web secondaire |
| Web Server 3 | 192.168.43.136 | Serveur web secondaire |
| Load Balancer | 192.168.43.140 | Répartition de charge |

**Technologies utilisées :**
- 🐧 **RHEL 7.9** (Red Hat Enterprise Linux)
- 🧰 **VirtualBox** (Virtualisation)
- ⚡ **Ansible** (Automatisation)
- 🔐 **OpenSSH** (Sécurité et accès)
- 🌐 **Apache HTTPD** (Hébergement Web)

---

## 🛠️ Étapes de Réalisation

### 1. Configuration de la Machine Master
- Création d’un utilisateur `ansible` avec privilèges sudo  
- Configuration du DNS local dans `/etc/hosts`  
- Installation et configuration d’**Ansible**  
- Configuration du fichier `ansible.cfg` et de l’inventaire  

### 2. Configuration des Nœuds Gérés
- Création d’un utilisateur `ansible` sur chaque nœud  
- Installation du package **OpenSSH client/server**  
- Génération et distribution de la clé SSH (`ssh-keygen` + `ssh-copy-id`)  
- Vérification de la connectivité SSH entre la Master et les nœuds  

### 3. Hébergement du Site Web
- Développement d’un site statique sous **HTML/CSS/Bootstrap**  
- Déploiement via un playbook Ansible (`site.yml`)  
- Installation et activation du service **HTTPD (Apache)**  

### 4. Mise en Place du Load Balancer
- Création de deux serveurs web secondaires  
- Configuration d’un **Load Balancer** via Ansible  
- Exécution du playbook `task.yml` pour automatiser la configuration  
- Test du basculement automatique entre serveurs  

---

## 📘 Structure du Répertoire Ansible
```text
ansible/
├── deploy-website.yml
├── task.yml
├── README.md
└── tasks/
    ├── ansible.cfg
    ├── inventory
    └── roles/
        ├── webserver/
        │   ├── tasks/main.yml
        │   ├── vars/main.yml
        │   └── handlers/main.yml
        └── loadbalancer/
            ├── tasks/main.yml
            ├── vars/main.yml
            └── handlers/main.yml
```

---

## 🚀 Résultats Obtenus

✅ Automatisation complète du déploiement et de la configuration des serveurs.  
✅ Sécurisation des connexions via SSH clés publiques/privées.  
✅ Hébergement réussi du site web de l’entreprise.  
✅ Répartition de charge fonctionnelle via Load Balancer.  

---

## 📚 Technologies et Outils Utilisés

| Domaine | Outils |
|----------|--------|
| OS | RHEL 7.9 |
| Virtualisation | VirtualBox |
| Automatisation | Ansible |
| Sécurité | SSH / OpenSSH |
| Web | Apache HTTPD |
| Langage de configuration | YAML |
| Éditeur | Visual Studio Code |

---

## 🧩 Mots Clés
`Ansible`, `SSH`, `OpenSSH`, `VirtualBox`, `RHEL`, `Load Balancer`, `Automatisation`, `Infrastructure`, `Apache`, `YAML`

---

## 🏁 Conclusion

Ce projet a permis de découvrir et de mettre en œuvre les concepts de **virtualisation**, **administration système** et **automatisation**.  
L’approche proposée a amélioré la **sécurité**, la **cohérence** et la **productivité** dans la gestion d’infrastructure d’IT24.  

Cette expérience a été une occasion d’apprentissage enrichissante, combinant théorie et pratique dans un contexte professionnel réel.

---

## 🔗 Références

- [Documentation officielle Ansible](https://docs.ansible.com/ansible/latest/getting_started/index.html)
- [Red Hat – Qu’est-ce qu’Ansible ?](https://www.redhat.com/fr/technologies/management/ansible/what-is-ansible)
- [Guide Red Hat – Configuration d’Ansible](https://www.redhat.com/sysadmin/configuring-ansible)
- [Déploiement d’un site web statique avec Ansible](https://www.redhat.com/sysadmin/deploying-static-website-ansible)

---

© 2023 – Ayoub SAMI | EHTP – IT24.MA
