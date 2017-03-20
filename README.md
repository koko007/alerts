# Alert form

### Jak by to melo vypadat?

![scr](/scr.png "Screenshot")

### Pouzite technologie
- Riot@2.6.X (bohuzel v 3.X.X je  stale plna chyb)
- Less
- Leaflet@7.7.0
- Slider pro vice hodnot: https://refreshless.com/nouislider/. Ukazka pouziti s cervenym podkladem: https://www.windytv.com/station/C0153
- Build system. Zvol si build system jaky chces, IMHO pro vyvoj muzes zvolit kompilaci less(u) a riot tagu primo v browseru. Bude to asi nejrychlejsi

### Styly
- Bude to vypadat stejne jako na https://origin2.windyty.com/beta.html > Menu > Settings
- Sirku odhaduji tak na 350px. Pro pouziti v mobilu to bude full screen.
- Podivej se na `variables.less`, ktere si muzes importovat do tvyho lessu a pak pouzivej styly z `plugins.less`, ktere uz jsou definovany ve Windtytv. Zakladni veci co pouzivej jsou `@myred, @backgroundWhite` a vsechny ikonky jsou definovany ve font family `iconfont`. Viz `styles.less` pro ukazku.
- Kdyztak si fonty stahni na lokal, Kacka vi kde.

### Preklady
- Prvni verze bude pouze v AJ. Az se to rozjede nahratime textove retezce a vse prelozime. Textove retezce zatim vladej primo do HTML, vyhazet je ven je hracka.

### Samotny formular
Jde do dolu postupne jak to prichazi. Vpravo na mape je nas WIndytacky picker, co se da posouvat. Pri posunu posle do formulare nove lat,lon (to delat nemusis)

**[ikonka Zvonku]  Never miss a big day. Set up alert for this location** - maly sedy text, ikonka @myred
Label: **Name of Alert**
**[ input text ]** - velky font. I kdyz se jedna o formular, stylovany je to tak, ze to vypada jako titulek. Text je defaultne predvypnen podle reverse GeoIP.
**Lat: number, lon: number** - normalni text, predvyplneny podle lokace markeru

**[ikonka vetru] Select wind conditions** - sekce
**< m/s > [input range slider]** - metrika (m/s) je klikaci a velikym fontem. Pri najeti mysi na ni se po obou stranach ukazi sipky a pri kliknuti se zmeni (na animaci se klidne vykasli ). Range slider zacina na 0m/s (vlevo) a konci cca na 40m/s. Pozor pro zmen metriky se ty hodnoty prepoctou na jinou metriku. K dispozici jsou metody W.overlays.wind.convertNumber, ktere budou ve finale k dispozici takze to nemusis resit. POZOR: Range slider rozsah neni spojity. 0-50% slideru zahrnuje vitr 0 - 10m/s, 50%-75% 10 - 20m/s, a zbylych 25% zabira zbytek
**vetrna ruzice** - kulata vetrna ruzice nakreslena jak byches chtit (SVG, obrazek, HTML5 - CSS3). Ma rozsah `N,NNW,NW,WNW,W,...`. Pri kliknuti na jednotlive sekce se sekce zabarvi na @myred aby bylo jasne, ze jsou vybrane. A ted pozor: Pri mouse over nad ruzici, se stejna ruzice objevuje i na mape v okoli naseho pickeru.







