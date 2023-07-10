# django-deures
django-deures

Projecte de Django


Per tal de poder pujar aquest projecte al github, en lloc d'usar token, he seguit les indicacions per fer-ho via SSH.
Localment em trobo a una distribució Debian.
Cal generar per a l'usuari local unes claus (pública i privada). Suposant que l'adreça de correu electrònic és usuari@correu.com, fem:

```
ssh-keygen -t ed25519 -C "usuari@correu.com"
```

(podeu deixar la contrasenya de la clau en blanc així no l'haureu de teclejar cada cop que calgui usar la clau)

Dins la carpeta ~/.ssh/, els fitxers id_ed25519 i id_ed25519.pub seran clau privada i pública, respectivament.

Posteriorment, cal entrar a github.com i a Settings > SSH and GPG keys > New SSH key (li donem un títol i copiem el text de la clau PÚBLICA (fitxer .pub) a la caixa de text "Key".
Piquem "Add SSH key". D'aquesta manera, el nostre projecte local podrà autenticar-se si el configurem amb l'URL remot per SSH.

```
mkdir elmeurepo
cd elmeurepo
git init
(creem el fitxer .gitignore, si cal)
git commit -m "primer commit"
git branch -M main
git remote add origin ssh://usuarigithub@github.com/usuarigithub/nom-repositori.git
git push -u origin main
```

Si us trobeu que ja havíeu definit el "git remote add origin" com a https://, podeu verificar-ho fent:
```
git remote -v
```
Si és https:// i el voleu canviar a ssh://, podeu fer:

```
git remote set-url origin ssh://usuarigithub@github.com/usuarigithub/nom-repositori.git
```
(un cop redefinit l'url, el projecte ja enllaça amb el repositori per ssh. Per exemple, un "git push -u origin main" posterior funcionarà).


