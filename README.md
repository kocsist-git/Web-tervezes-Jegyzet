# HTML5-Jegyzet

#### A kezdet: 
A kezdetek, egy szabványos HTML5 oldal nyomában: 
A html dokumentumunk legelső sora a dokumentum típusának meghatározása. 
Ezt a <!DOCTYPE html> információs szöveg elhelyezésével tehetjük meg. Ezzel tudatjuk a böngészővel milyen dokumentumra felolvasására számítson. Nem tekintjük html tag -nek. (DTD)

Következő sorban el is kezdhetjük felépíteni a html oldalunkat. 
Ehhez a `<html> … </html>` objektumot használjuk. 
Itt megadható a html oldalunk alapértelmezett nyelve. 
`<html lang="hu">` Ennek elhagyása nem sérti a HTML5 szabványt, de egy Warning kapunk cserébe. 
Az ajánlás a következő: Mindig használjuk `<html lang="hu">` tag-et. Az itt meghatározott nyelvet örökölni fogja a többi html tag is. 

Felvetődik a kérdés, hogy mennyire fontos a validitás? Van -e értelme egyáltalán azzal vesződni, hogy tökéletesen megfeleljünk a HTML5 szabványnak. 
Nos… A legtöbb böngésző képes megjeleníteni a szabványtól eltérő html kódot. Ennek ellenére Én úgy gondolom mindenképp törekednünk kell, az igényes munkára. A hibák és figyelmeztessek kijavításával a html tag-ek helyes használatával, garantálhatjuk a minőséget. 
HTML5 szabványt a W3C gondozza. 
A szabványok betartása garantálja továbbá az eszköz és böngésző függetlenséget. 
Következő objektum a `<head> … </head>` páros. Megfigyelhető, hogy ő rendelkezik egy lezáró tag-el is. Általában ilyen tag-eket fogunk használni. Ebben az objektumba helyezzük ez a dokumentumra vonatkozó meta információkat. A `<head>` objektumba meg kell adnunk a dokumentum kódolását. Ezt a ` <meta charset="UTF-8">` tag-el tehetjük meg. 

Léteznek üres típusú objektumok ez azt jelenti, hogy nem is tehetünk bele semmit. Tehát a nyitó és záró tag között nem szerepelhet semmi.
A html objektumok egymásba is ágyazhatók. Erre rögtön nézünk is példát. Fontos megjegyezni, hogy az átlapolás nem megengedett.
Következzen egy egyszerű szabványos html5 oldal. 

```
<!DOCTYPE html>
<html lang="hu">
<head>
   <title>Document</title>
</head>
<body>
    
</body>
</html>
```
Ez egy szabványos html5 oldal. Ezt ellenőrizhetitek a https://validator.w3.org/ oldalon. 
Két számunkra ismeretlen objektumot látunk benne. `<title> … </title> valamint a <body> … </body>`
A `<body>` a dokumentum törzse. Az itt megfogalmazott objektum kapcsolatok kerülnek megjelenítésre a böngésző által. 
A `<title>` adja meg a dokumentum címét. 

Mi az a dokumentumrészfa? DOM (Document Object Model)
Leírja, hogy hogyan épül fel az adott dokumentum. Az egyes objektumok egymásba ágyazhatók. A fa csúcspontja mindig a szülő a gyermek objektumok belőlük ágaznak le. 

Megjegyzések is elhelyezhetők a html oldalban. `<!—Ez egy megjegyzés -->`

Az objektumoknak van alapértelmezett formázása. A böngésző ennek megfelelően jeleníti meg őket. Egy objektumok lehet blokkszintű, vagy sorszintű. 

Blokkszintű: megadhatók a méretei. pl. Előtte, utána térköz. 

Sorszintű(inline): a méretét a tartalom határozza meg. 

Fontos NE az objektumokat használjuk formázásra. Arra a CSS való. 

Objektumok azonosítása: 
id = egyedi egy dokumentumon belül. 
class = objektumok csoportosítása. Egy objektum több csoportba is tartozhat, egy csoport több objektumhoz is tartozhat. 
hint: a csoportnevek ne a hatásra, hanem a funkcióra utaljanak. 

Jó-jó, ha ne formázásra használjuk a különböző html tag-eket, akkor mit használjuk formázásra?   

#### A CSS: 

Több helyen is adhatunk meg CSS utasítást. A <head> tegben elhelyezve. A <body> -ban elhelyezve. Az objektumba ágyazva, úgynevezett inline CSS-ként, vagy külső fájlban. 

Mi az utóbbit fogjuk választani. Tehát külső fájlban határozzuk meg a CSS szabályokat. 

A böngésző fentről lefele olvassa és alkalmazza a szabályokat. Ökölszabályként megjegyezhető, hogy mindig az utolsó CSS szabályt fogja végül megjeleníteni. 

Két részre oszthatjuk a CSS parancsot. Kijelölő és meghatározó blokk. 
Melyik html objektumot akarjuk formázni, és hogyan akarjuk, hogy kinézzen. 

Alapvető kijelölők:
- Típus kijelölő:
Az összes adott típusú HTML objektumot kijelöli. 
p {color: blue;} – minden bekezdés betű színé kék lesz.
- Azonosító kijelölő
Az adott ID val rendelkező objektumot jelöli ki. 
- Osztály kijelölő
adott class értékkel rendelkező objektumokat jelöli ki. 
- Univerzális kijelölő
csillag * = minden HTML objektumra vonatkozik.

Öröklődés:
Gyermek örököl a szülőtől. Gondoljuk vissza a dokumentum fára. 
Képlet esetén nem a képlet, hanem a kiszámított értők öröklődik. 
Az öröklés felülírható a tulajdonság újbóli megadásával. 
Az öröklés megtagadható az initial érték használatával. 
A nem alapértelmezett öröklés kérhető az: inherit értékkel. 

Színek megadása:
- Névvel:
előre defibiált színnevek. pl. Red
- Hexadecimális RGB:
additív színkeverés vörös, kék, zöld. pl. #FF6347
- Decimális RGB:
0-255 közöti számokkal, vagy 0% - 100% ig. pl. rgb(255, 99, 71)
- Százalékos RGB:
HSL kóddal:
hsl(hue, saturation, lightness)
pl. hsl(156, 40%, 27%)

CSS fájlban így írhatunk megjegyzést: /* ez egy megjegyzés */
