h1. Comprendre les réglages dans gitconfig

h3. Définition des branches remotes

[branch "42248-outbrain-temp"]
  remote = origin
  merge = refs/heads/42248-outbrain-temp

* origin est le nom par défaut pour le serveur centralisé optionnel.
* merge indique dans quelle branche doivent être mergés les modifs 