# level 15: 
```sh
cd /home/level/15_live_rfi/
```
15_live_rfi est inaccessible

On se dirige alors vers le site web et il nous propose un site "https://rfi.warchall.net/" pour trouver la solution

Il y a deux images avec leurs textes alternatifs(alt), "EN" et "DE" qui ne sont pas le plus important.

Dans l'url suivant, X change en fonction de l'image qu'on touche: "https://rfi.warchall.net/index.php?lang=X"

X peut être soit "en" ou "de". Alors pour faire une injection LFI (Local File Inclusion), je change X par: php://filter/convert.base64-encode/resource=solution.php

On appelle cela un wrapper
```sh
https://rfi.warchall.net/index.php?lang=php://filter/convert.base64-encode/resource=solution.php
```
Un code en base 64 apparaît alors, que je copierai et décoderai

Un fichier php apparaît et cela affiche "NOTHING HERE" mais il faut rester vigilant jusqu'à la fin car, en effet la solution se trouve au pied du code php

La solution a été retrouvée
