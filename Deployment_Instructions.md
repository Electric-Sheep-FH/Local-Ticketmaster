
# Guide simple pour lancer TicketMaster en local

Ce tutoriel explique **pas à pas**, comment télécharger et lancer l'application TicketMaster en local, même si vous êtes débutant.

---

## ✅ **Étape 1 : Installer Docker Desktop**

Docker permet de lancer facilement l'application en local.

- Téléchargez Docker Desktop sur le site officiel
- Installez Docker Desktop :
    
    - Suivez simplement les instructions d'installation (Windows, Mac ou Linux).
    - Après installation, lancez Docker Desktop.
- Vous pouvez vérifier la bonne installation de docker et docker compose en saisissant dans un terminal les commandes suivantes :
```bash
docker --version
docker-compose --version
```
⚠️ **Important (Windows)** :  
Assurez-vous que la virtualisation soit activée sur votre ordinateur.

---

## ✅ **Étape 2 : Télécharger les fichiers nécessaires**

- Rendez-vous sur le dépôt GitHub suivant :  
    https://github.com/Electric-Sheep-FH/Local-Ticketmaster
    
- Téléchargez le projet en cliquant sur :
		Code -> Download ZIP
![[Pasted image 20250313151400.png]]
- Décompressez le fichier téléchargé où vous le souhaitez sur votre ordinateur.

## ✅ **Étape 3 : Lancer l’application TicketMaster**

- Ouvrez un terminal :
    
	- **Windows** : Lancez `PowerShell` (clic droit → ouvrir avec PowerShell dans le dossier téléchargé).
	- **Mac** : Lancez l'application `Terminal`, puis déplacez-vous dans le dossier décompressé avec :
		```bash
		cd ~/Downloads/Local-Ticketmaster-main
		```
	- **Linux** : Ouvrez un terminal et allez dans le dossier décompressé.

- Une fois dans le chemin affiché du dossier téléchargé (où se trouve le fichier `docker-compose.yml`), tapez simplement :
	```bash
	docker compose up
	```

- Attendez que Docker télécharge et lance automatiquement l'application et la base de données (cela peut prendre quelques minutes au premier démarrage).

Lorsque vous voyez ce type de message :

```mathematica
web_1 | Application started...
```

## 🌐 **Étape 4 : Accéder à l’application**

- Ouvrez votre navigateur internet (Chrome, Firefox, Edge…)
- Rendez-vous à l’adresse suivante :  
    [http://localhost:5000](http://localhost:5000)

Vous voyez désormais l'application **TicketMaster** en fonctionnement sur votre machine !

## 🎉 **Bravo, vous avez réussi !**

Vous avez désormais lancé localement l'application **TicketMaster** grâce à Docker !

## 🛑 **Pour arrêter l'application**

Dans votre terminal, appuyez simplement sur :
```bash
Ctrl + C
```

Ou pour arrêter complètement les conteneurs Docker :
```bash
docker compose down
```

## 💬 **Problèmes courants & astuces**

- **Port occupé ?** Si le port 5000 ou 3306 est déjà utilisé par votre machine, vous pouvez changer les ports dans le fichier `docker-compose.yml` :
```yaml
ports:
  - "5001:80"  # changez 5000 par 5001 par exemple
```

- **Problème de démarrage ?** Essayez :
```bash
docker compose down -v
docker compose up
```

## 🔧 **Plan de maintenance**

Prévoir un calendrier de maintenance régulier pour appliquer les mises à jour et les correctifs de sécurité nécessaires. Testez les mises à jour sur un environnement de staging avant de les appliquer en production.