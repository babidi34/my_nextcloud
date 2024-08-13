# README

## Procédure de restauration de Nextcloud
1. Déployer Nextcloud avec Ansible

Lancez le playbook Ansible pour déployer Nextcloud :

```
ansible-playbook deploy_nextcloud.yml --vault-password-file .env
```
2. Restaurer le dernier snapshot avec Restic

Restaurer le dernier snapshot de votre backup Restic sur le répertoire /mnt/nextcloud-backup/ :

```
restic restore latest --target / # (l'arborescence /mnt/nextcloud-backup/ fais déjà partie du snapshot)
```
3. Lancer un tunnel SSH vers le serveur

Créez un tunnel SSH pour accéder à l'interface Nextcloud AIO :

```
ssh -L 8080:localhost:8080 user@remote_server_ip
```

Remplacez user par votre nom d'utilisateur et remote_server_ip par l'adresse IP de votre serveur.
4. Accéder à l'interface Nextcloud AIO

Ouvrez votre navigateur et allez à l'adresse suivante :

https://localhost:8080

5. Restaurer la sauvegarde

Dans l'interface Nextcloud AIO, choisissez l'option "Restore" et indiquez le chemin du backup restauré dans /mnt/nextcloud-backup/.