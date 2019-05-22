## H2 - WebGoat -tehtävä, MITRE Att&ck -tekniikka

http://terokarvinen.com/2019/penetration-testing-tunkeutumistestaus-ict4tn027-3004-intensive-summer-course-2019-w21w22-5-credits

#### Tehtävänanto:

1. [Ratkaise jokin WebGoatin tehtävä. Hyödynsitkö jotain OWASP10 -haavoittuvuutta? Mitä niistä?](#tehtava1)

2. [Mainitse esimerkki MITRE:n Att&ck tekniikasta, joka soveltuu weppiin. Osaatko antaa esimerkin hyökkäyksestä tai haittaohjelmasta, jossa sitä on käytetty?](#tehtava2)

---

#### <a id="tehtava1">1. WebGoat, Silent Transactions Attack</a>

Jatkoin siitä kohdasta mihin luennolla tänään jäin, eli AJAX Security - Silent Transactions Attack:\
![silent-transaction-attack](/h2-webgoat-mitre/screenshots/silent-transaction-attack.png)

Tehtävänä oli siis vaivihkaa suorittaa tilisiirto.\
Aiempien AJAX Security -tehtävien perusteella ajattelin, että DOM:ia manipuloimalla voisi ehkä tämänkin suorittaa. Avasin siis Firefoxilla sivun lähdekoodin (right click -> View Page Source), mutta sieltä ei löytynyt mitään mielenkiintoista:\
![page-source](/h2-webgoat-mitre/screenshots/page-source.png)

Seuraavaksi kokeilin valita hiirellä tehtäväalueen sivulta ja View Page Sourcen sijasta klikkasin View Selection Source:\
![selection-source](/h2-webgoat-mitre/screenshots/selection-source.png)

Ainoa asia mikä tässä iski silmääni, oli tuo mystinen `silentTransaction.js`-tiedosto. Avasin sen:\
![js-source](/h2-webgoat-mitre/screenshots/js-source.png)

`processData` ja `callback` -funktioissa ei ole mitään mielenkiintoista, mutta `submitData` sen sijaan ottaa argumentteja.\
Avasin Firefoxin kehitystyökaluista konsolin ja huomasin, että siinä on autofill-ominaisuus, joka kiltisti täydentää komentoja:\
![autofill](/h2-webgoat-mitre/screenshots/autofill.png)

How nice. Tällähän voisi siis sokkona lähteä kokeilemaan mitä tuhoa on mahdollista saada aikaan.

Suoritan funktion antamalla `accountNo`-argumentiksi `1337` ja `balance`-argumentiksi `31337`:\
![js-function](/h2-webgoat-mitre/screenshots/js-function.png)

Tehtävä purkissa:\
![success](/h2-webgoat-mitre/screenshots/success.png)

---

#### <a id="tehtava2">2. MITRE Att&ck</a>

// TODO
