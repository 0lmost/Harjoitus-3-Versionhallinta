# Harjoitus 3 - Versionhallinta

Tehtävien teko aloitettu 19.4.2022 klo 13:30

**Bold** Laitteen/alustan tiedot, jolla tehtävä suoritettiin:

    Oracle VirtualBox Version 6.1.32 r149290 (Qt5.6.2)
    Debian 11.3
    6000 MB RAM
    60 GB Levytilaa

## z) Lue ja tiivistä 

[MarkDown-artikkeli](https://commonmark.org/help/)

- Ohejeita tekstin ja koodin muotoiluun markdownissa.

## a) MarkDown 

Tee tämän tehtävän raportti MarkDownina. Helpointa on tehdä raportti GitHub-varastoon, jolloin md-päätteiset tiedostot muotoillaan automaattisesti. Tyhjä rivi tekee kappalejaon, risuaita ‘#’ tekee otsikon, sisennys merkitsee koodinpätkän.

Ensiksi tein githubiin uuden varaston ja laitoin sinne README tiedoston ja laitoin varastolle vapaan lisenssin. Sen jälkeen kopioin SSH linkin ja avasin terminaalin Debianissa ja laitoin komennon

	$ git clone git@github.com:0lmost/Harjoitus-3-Versionhallinta.git

Tämä teki kansion Debianiin, joka on siis linkattu tuohon github-varastoon. Sitten aloin tekemään tätä tehtävää sinne luomalla tiedoston

	$ micro Harjoitus-3.md

Kun suoritin git add ja commit sekä git push ja pull ja menin githubiin katsomaan, miltä seillä näyttin niin huomasin, että olin vahingossa nimennyt tiedoston vain nimellä md, joten se ei ollit MarkDown muodossa, joten korjasin nimeämällä tiedoston uudestaan Harjoitus-3.md


## b) Pull first

Tee useita muutoksia git-varastoosi. Tee muutama muutos, jossa yksi commit koskee useampaa tiedostoa. Anna hyvä kuvaukset (commit message), yksi englanninkielinen lause imperatiivissa (määräysmuodossa) "Add top level menu to Foobar synchronizer"


## b) Kaikki kirjataan

Näytä omalla git-varastollasi esimerkit komennoista ‘git log’, ‘git diff’ ja ‘git blame’. Selitä tulokset.

		$ git log

Selvittää varastoon tehdyt muutokset eli commitit. Logista selviää tarkat tiedot mm. token, muutoksen tekijä ja aika milloin muutos tehtiin ja commit viesti.


		$ git diff


Kuten nimi hieman kertoo, komento näyttää erot tiedostoissa, jos vaikka ei oli vielä committanut muutoksia niin näyttää erot githubiin verrattuna + merkillä. Ei näytä mitään, jos muutoksia ei ole tehty.


		$ git blame


Komento osoittaa suoraan itse syylliseen eli näyttää suoraan kuka on tehnyt mitäkin työtä tiedostossa eli kuka on kirjoittanut minkä rivin. Aluksi komento ei näyttänyt minulle mitään, mutta googlasin ja löysin hyvän selityksen.
Piti laittaa tiedoston nimi komennon perään niin komento toimi.
Lähde: [Git Blame Explained with Examples](https://www.freecodecamp.org/news/git-blame-explained-with-examples/) Luettu 19.4.2022


## c) Huppis!

Tee tyhmä muutos gittiin, älä tee commit:tia. Tuhoa huonot muutokset ‘git reset --hard’. Huomaa, että tässä toiminnossa ei ole peruutusnappia.

Aloitin

## d) Formula

Tee uusi salt-tila (formula, moduli, infraa koodina). (Eli uusi tiedosto esim. /srv/salt/terontila/init.sls). Voit tehdä ihan yksinkertaisen parin funktion (pkg, file...) tilan, tai edistyneemmin asentaa ja konfiguroida minkä vain uuden ohjelman: demonin, työpöytäohjelman tai komentokehotteesta toimivan ohjelman. Käytä tarvittaessa ‘find -printf “%T+ %p\n”|sort’ löytääksesi uudet asetustiedostot.

