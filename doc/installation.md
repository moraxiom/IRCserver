# Installation et configuration du serveur IRC et ses services
Ces étapes permettent l'installation et la configuration d'un serveur IRC à l'aide de*WeeChat* et *InspIRC* avec les 
réseaux *OFTC*, *Libera.chat*, *Undernet* et *ircnet*.

## A. Avoir assez de mémoire
Afin d'être sûr d'avoir assez de mémoire, on peut créer un fichier système *swapfile* qui déplace la mémoire vive
surchargée dans la mémoire de stockage, et ce de façon temporaire. **Il est FORTEMENT recommandé de le faire si 
une ligne quelconque de vos *logs* ressemble à ceci :**
```
systemd[1]: mysql.service: A process of this unit has been killed by the OOM killer.
```
1. Créer et allouer un fichier système de 512 MB<br>**Évidemment, connectez-vous à votre serveur avant.**</br>
```
sudo fallocate -l 512m /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
```
2. Activer et automatiser l'utilisation du fichier dans le *fstab*<br>Le *fstab* gère les fichiers système d'une
machine quelconque.</br>
```
sudo swapon /swapfile
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
```
3. Valider l'ajout de la ligne (avec *echo*) dans le *fstab* avec l'éditeur *jed*
```
sudo jed /etc/fstab
```

## B. Client WeeChat
1. Télécharger le client WeeChat. Lorsqu'on vous le demande, entrez "Y" et appuyer sur la touche *Enter* afin de procéder à l'installation.<br>Vous pouvez
réinitialiser les services qui ont besoin de l'être.</br>
```
sudo apt-get install weechat
```
2. Ouvrir le logiciel
```
weechat
```
