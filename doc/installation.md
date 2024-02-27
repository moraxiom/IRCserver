# Installation et configuration du serveur IRC et ses services

## A. Avoir assez de mémoire
Afin d'être sûr d'avoir assez de mémoire, on peut créer un fichier système "swapfile" qui déplace la mémoire vive
surchargée dans la mémoire de stockage, et ce de façon temporaire. **Il est FORTEMENT recommandé de le faire si 
une ligne quelconque de vos *logs* ressemble à ceci :**
```
systemd[1]: mysql.service: A process of this unit has been killed by the OOM killer.
```
