## H4 - HackTheBox

http://terokarvinen.com/2019/penetration-testing-tunkeutumistestaus-ict4tn027-3004-intensive-summer-course-2019-w21w22-5-credits

#### Tehtävänanto:

1. [Hedelmiä matalalla. Mitkä vaikuttavat HackTheBoxin helpoimmilta kohteilta? Tiedustele HackTheBox-verkko esimerkiksi porttiskannerilla ja ryömijällä. Noudata Rules-kohdassa annettua scopea.](#tehtava1)

2. [Bonus: murtaudu jollekin HackTheBoxin maalikoneelle. Voit katsoa weppiliittymästä vinkkiä siitä, mitkä koneet ovat helppoja.](#tehtava2)

---

#### Aloitus: Kali + QEMU

En halunnut käynnistää Kalia USB-tikulta, joten kokeilin huvikseni [QEMU:a](https://www.qemu.org).

Ensimmäinen yritys, jossa avaan USB-tikulla olevan Kalin virtuaalikoneeseen:\
![kali-qemu-1](/h4-hackthebox/screenshots/kali-qemu-1.png)
![kali-qemu-2](/h4-hackthebox/screenshots/kali-qemu-2.png)
![metasploit-run](/h4-hackthebox/screenshots/metasploit-run.png)

Helei, näytti toimivan heittämällä.\
Ilo ei valitettavasti kestänyt kauaa, sillä virtuaalikone kaatui. Kyseessä on ilmeisesti [tunnettu bugi MacOS:ää käyttäessä](https://bugs.launchpad.net/qemu/+bug/1818937). Sain Kalin ja QEMUn toimimaan yhdessä pitkällisen säätämisen jälkeen seuraavilla optioilla:\
![kali-qemu-3](/h4-hackthebox/screenshots/kali-qemu-3.png)

`qemu-live-x86()` käynnistää Kalin USB-tikulta, `qemu-disk-x86()` käynnistää virtuaalikoneen käyttäen qcow2-levykuvaa, jolle Kali on asennetty, ja `qemu-install-x86()` käynnistää Kalin USB-tikulta ja avaa myös qcow2-levykuvan, jolle Kalin voi sitten asentaa. Muistutukseksi, että levukuvan täytyy olla riittävän iso. Asennettuna Kali vie yli 10GB.

---

#### <a id="tehtava1">1. [HackTheBox](https://www.hackthebox.eu) kohteita</a>

TODO

---

#### <a id="tehtava2">2. HackTheBox murtautuminen</a>

TODO
