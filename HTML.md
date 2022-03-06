# HTML5-Jegyzet

### A kezdet: 
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
Két számunkra ismeretlen objektumot látunk benne. `<title> … </title>` valamint a `<body> … </body>`
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

### A CSS: 

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
előre definiált színnevek. pl. Red
- Hexadecimális RGB:
addiktív színkeverés vörös, kék, zöld. pl. #FF6347
- Decimális RGB:
0-255 közöti számokkal, vagy 0% - 100% ig. pl. rgb(255, 99, 71)
- Százalékos RGB:
HSL kóddal:
hsl(hue, saturation, lightness)
pl. hsl(156, 40%, 27%)

CSS fájlban így írhatunk megjegyzést: /* ez egy megjegyzés */

`<main> ... </main>` az oldal fő tartalmi szakasza. Csak egy lehet belőle. Nem lehet gyermekelem. Akadálymentesítési szempontból is fontos. 

`<article> ... </article>` Ez egy önállóan is értelmes tartalmi egységet jelöl. A tartalmi egységek egymásba ágyazhatók. pl. tartalmi egysége lehet egy fórum. A fórumba írt bejegyzések is kerülhetnek `<article>` -tag-ek közé. 

`<section> ... </section>` Szakasz. Azonos témakörben tartozó több beágyazott tartalom közös címmel. Környezetének kontextusában nyer értelmet. Egymásba ágyazható. 

`<figure> ... </figure>` Erősen kapcsolódó tartalom megjelölésére szolgál. pozíciójának megváltoztatása az oldalon nem befolyásolja az oldal tartalmának érthetőségét. pl. ábrák, diagramok, képek, videók. stb.
Ehhez tartozhat `<figcaption>` Ami a kapcsolódó tartalom címét jelenti meg. 

`<aside> ... </aside>` Gyengén kapcsolódó tartalom. Érintőleges, nem a témáról szóló tartalom. pl. további információk, szavak magyarázata, idézetek, oldalsávban címfelhők, kapcsolódó reklám. 

`<nav> ... </nav>` Navigációs elem. Menüsor, lapszámozás. Oldalon belüli navigálást megvalósító elemek helye. 

`<header> ... </header>` Fejléc, bármilyen tartalmi egység elején a bevezető tartalom megadásra.

`<footer> ... <footer>` Lábléc, bármely tartalmi egység alján. pl. szerző, linkek, jogi következmények, elérhetőségek megadására. 

`<h1...6>` Címsorok fontos része egy oldal tartalmának. SEO és akadálymentesítés szempontjából is komoly jelentőségé van. 
6 szintet különböztetünk meg. 
A legfontosabb a `<h1>`
NEM FORMÁZÁSRA HASZNÁLJUK!!!
Mindig legyen az oldalon `<h1>` -es címke és csak egy legyen belőle. Lehetőleg a `<body>` és az első tartalmi elem között helyezkedjen el. 

### Szövegek strukturális elemei:

Szövegek tagolása: 
A TAB, több szóköz a HTML forráskódban megjelenik, de a felhasználónál már nem. 
A blokkszintű objektumok külön sorban jelennek meg. (css-el megváltoztatható) 
A sor szintűek nem eredményeznek sortörést.
`<p> ... </p>` bekezdés. Blokk szintű
`<br>` sortörés. manuális. Ne használjuk térköz és bekezdés helyett. 
`<wbr>` feltételes sortörés. Szavak elválasztását adjuk meg. 
`<pre> ... <pre>` Előreformázott szöveg. tartalmilag olyan jellegű a szöveg, hogy figyelembe kell venni a tördelést. pl. ASCII-ábra, képversek, dalszövegek fölé írt akkordok. 

Szemantikus tartalmak:
`<cite>` A mű címe, vagy URL-je.
`<blockquote> ... </blockquote>` idézetblokk, oldal szerkezet jellegű. Nagy terjedelmű idézetekhez. Tartalmazhat más oldalszerkezeti elemeket is. Lehet `<cite>` tulajdonsága. 
`<q> ... </q>` Bekezdésen belüli idézetek. Nem tartalmazhat más oldalszerkezeti elemeket. Az idézőjelent nem kell kitenni a böngésző gondoskodik róla. 
`<def> ... <def>` Azt a szót jelöli meg egy bekezdésben, amit azt adott bekezdésben definiáltunk. 
`<abbr title = "..."> ... </abbr>` Rövidítés. Valaminek a rövidítését adjuk meg. 
`<small> ... </small>` Megjegyzés. Csak rövid szövegre használható. Nem használható bekezdésre, vagy szakaszra.
`<sub> ... </sub>` és `<sup> ... </sup>` Alsó és felső index. 
`<code> ... </code>` Programkódot jelöl. 
`<var> ... </var>` Programban, matematikai kifejezésben megjelenő változók. 
`<time datetime= "..."> ... </time>` Datetime= a gép számára értelmezhető dátum. Tag-ek közé pedig a felhasználó számára értelmezhető dátum kerül. 

Funkcionális elemek:
`<s> ... </s>` Nem pontos idejétmúlt tartalom. 
`<samp> ... </samp>` Program kimenete, üzenet. 
`<kbd> ... </kbd>` Felhasználó által beírandó, vagy kimondandó tartalmon. pl. a betűméret nevelése érdekében a CTRL + Gombokat nyomja le. 

Kiemelések:
`<em> ... </em>` Hangsúlyozás. A tartalom hangsúlyozása módosíthatja a szöveg értelmét. A felolvasó programok más hangsúllyal olvassák fel. 
`<strong> ... </strong>` fontos tartalom esetén. A felolvasó programok más hangsúllyal olvassák fel. 
`<b> ... </b>` Figyelem felhívás, de nem különösen fontos.  A felolvasó programok nem hangsúlyozva olvassák fel. 
`<mark> ... </mark>` Vizuális kiemelés. A kiemelt szöveg magában is megálja a helyét. 

Kiemelések tipikus használata: 
Egy idézetben MI jelölünk ki egy szövegrészt, akkor használhatjuk a `<mark>`-ot. Ha a szerző emelte ki, akkor `<em>`, vagy `<strong>` használata javasolt. 

További felhasználása a `<mark>` jelölőnek: 
Keresési eredmények megjelölése, rendszeresen frissített listában az új elemek jelölésére, a naptában az aktuális nap megjelölésére. 

`<u> ... </u>` Helytelenül írt szöveg megjelölésére. Csak nagyon indokolt esetbe használjuk. 
`<i> ... </i>` Szövegrész elkülönítésére, szakkifejezés, cím, más nyelvű, más hangulatú szöveg elkülönítésére használjuk.

Szerkesztések: 
`<del> ... </del>` Törölt szöveg. Megjelenő szöveg, de jelezzük, hogy érvénytelen. Megadható `<cite>` miért töröltük és `<datetime>` törlés időpontja.
`<ins> ... </ins>` Utólagosan beszúrt tartalom. Itt is megadható a miért és mikor. 

Hivatkozások: 
`<a herf = " ... "> ... </a>` Tag-ek között adjuk meg a felhasználónak megjelenő szöveget. A `herf` után pedig a címet. 
Megadható tulajdonságok:
download: a cél egy letöltendő fájl értéke a fájl alapértelmezett neve. 
hreflang: a céloldal nyelve.
type: a cél MIME típusa. 

rel értékei: 
alternate: azonos tartalom alternatív (más nyelvű vagy típusú) formában.
author: a szerző bemutatása. 
external: a webhelyen kívüli (külső) oldal
help: az aktuális csúcspont szülőjére és annak gyerekeire vonatkozó segítség

target értékei:
hol jelenjen meg a hivatkozott URL?
keret = iframe, ablak, lap = böngészési környezet
nev: a név nevű keretben
_parent: a szülőkeretben ➢ szülő hiányában: _self
_top: a legfelsőbb szintű (legősibb) szülőkeretben ➢ szülő hiányában: _self
_self: ugyanabban a keretben (alapértelmezett)
_blank: új keretben

Csak indokolt esetekben térjünk el az alapértelmezéstől!

Alapértelmezett célmappa és böngészési környezet megadása:
`<base href = " ..." />` Megadható az alapértelmezett relatív útvonal. 
Érdemes mindig relatív linket használni. 

A hivatkozásoknak 4 fő állapota van. 
1. a felhasználó még nem kereste fel. 
2. a felhasználó már felkereste.
3. az egér fölötte van.
4. éppen töltődik az oldal. 

Ezeknek a formázását CSS alosztály kijelölővel végezzük.

`a:link` a felhasználó még nem kereste fel. 
`a:visited` a felhasználó már felkereste.
`a:hover` az egér fölötte van.
`a:active` éppen töltődik az oldal. 

A felkeresett oldalt a böngészési előzményekből kéri le a böngésző.

Szövegek tulajdonságai:
`lang = " ... "` Bármilyen tag esetén megadható. "HU" - magyar. "EN" - angol. 
Akadálymentesítés szempontjából fontos. SEO szempontból is hasznos. 

Speciális karakterek:
Numerikusan: 
`&#nnnn;` decimális
`&#xhhhh;` hexadecimális

Karakterentitás: 
& `&amp;` , vagy `&#38;`
" `&quot;`, vagy `&#34;`
stb.


Egy kevés CSS:

Sövegek formázása:
Távolságok, tördelések:
Betűköz: `letter-spacing`
Szóköz: `word-spacing`
Sormagasság: `line-height`
Tördelésék és white space tulajdonságok: `white-space`

Igazítások:
`text-aling` vízszintes, blokk szintű elemekre. 
`vertical-aling` függőleges, ez inline elemekre, vagy táblázat cellákra, nem öröklődik
`text-indent` bekezdések behúzása.

Átalakítások:
`text-transform` 
`font-variant`
`font-family` vesszővel elválasztva megadható több család is. A böngésző az első telepítettet fogja használni. 

`font-size` Betűméret. 
`font-style` 
`font-weight` 

További formázások:
-`text-decoration` 
-`text-decoration-line`
-`text-decoration-style`
-`text-decoration-color`

-`text-shadow` Szövegárnyék. 