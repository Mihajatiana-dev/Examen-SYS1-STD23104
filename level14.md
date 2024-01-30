# level 14: 
```sh
cd /home/level/14_live_fi/
```
14_live_fi est inaccessible

On se dirige alors vers le site web et il nous propose un site "https://lfi.warchall.net/" pour trouver la solution

Il y a deux logo, le drapeau américain et allemand et dans l'url suivant, X change en fonction du logo qu'on touche: "https://lfi.warchall.net/index.php?lang=X"

X peut être soit en ou de. Alors pour faire une injection LFI (Local File Inclusion), je change X par: php://filter/convert.base64-encode/resource=solution.php

On appelle cela un wrapper
```sh
https://lfi.warchall.net/index.php?lang=php://filter/convert.base64-encode/resource=solution.php
```

Un code en base 64 apparaît alors, que je copierai et décoderai

Un fichier php apparaît et la solution s'y trouvera
