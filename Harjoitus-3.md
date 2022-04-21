# Harjoitus 3 - Versionhallinta

Tehtävien teko aloitettu 19.4.2022 klo 13:30 | Lopetettu klo 16:30

**Laitteen/alustan tiedot, jolla tehtävä suoritettiin**

    Oracle VirtualBox Version 6.1.32 r149290 (Qt5.6.2)
    Debian 11.3
    6000 MB RAM
    60 GB Levytilaa

## z) Lue ja tiivistä 

[MarkDown-artikkeli](https://commonmark.org/help/)

- Ohjeita tekstin ja koodin muotoiluun markdownissa.

## a) MarkDown 

Tee tämän tehtävän raportti MarkDownina. Helpointa on tehdä raportti GitHub-varastoon, jolloin md-päätteiset tiedostot muotoillaan automaattisesti. Tyhjä rivi tekee kappalejaon, risuaita ‘#’ tekee otsikon, sisennys merkitsee koodinpätkän.

Ensiksi tein githubiin uuden varaston ja laitoin sinne README tiedoston ja laitoin varastolle vapaan lisenssin. Sen jälkeen kopioin SSH linkin ja avasin terminaalin Debianissa ja laitoin komennon

![image](https://user-images.githubusercontent.com/60943507/164013544-f5b09e8d-8a2b-444e-a735-98e3bbda87a2.png)


	$ git clone git@github.com:0lmost/Harjoitus-3-Versionhallinta.git

Tämä teki kansion Debianiin, joka on siis linkattu tuohon github-varastoon. Sitten aloin tekemään tätä tehtävää sinne luomalla tiedoston

	$ micro Harjoitus-3.md

Kun suoritin git add ja commit sekä git push ja pull ja menin githubiin katsomaan, miltä siellä näytti niin huomasin, että olin vahingossa nimennyt tiedoston vain nimellä md, joten se ei ollit MarkDown muodossa, joten korjasin nimeämällä tiedoston uudestaan Harjoitus-3.md


## b) Pull first

Tee useita muutoksia git-varastoosi. Tee muutama muutos, jossa yksi commit koskee useampaa tiedostoa. Anna hyvä kuvaukset (commit message), yksi englanninkielinen lause imperatiivissa (määräysmuodossa) "Add top level menu to Foobar synchronizer"

Tehtävää tehdessä tein useita committeja ja annoin uusia commit viestejä ohjeen mukaisesti.

## b) Kaikki kirjataan

Näytä omalla git-varastollasi esimerkit komennoista ‘git log’, ‘git diff’ ja ‘git blame’. Selitä tulokset.

		$ git log
		
![image](https://user-images.githubusercontent.com/60943507/164012965-91377576-c24f-41b8-8768-c0b8710baff4.png)
	

Selvittää varastoon tehdyt muutokset eli commitit. Logista selviää tarkat tiedot mm. token, muutoksen tekijä ja aika milloin muutos tehtiin ja commit viesti.


		$ git diff


Kuten nimi hieman kertoo, komento näyttää erot tiedostoissa, jos vaikka ei oli vielä committanut muutoksia niin näyttää erot githubiin verrattuna + merkillä. Ei näytä mitään, jos muutoksia ei ole tehty.


		$ git blame
		
![image](https://user-images.githubusercontent.com/60943507/164013193-08b0b09f-3d3a-4bf0-b207-22c0a1c92d4b.png)



Komento osoittaa suoraan itse syylliseen eli näyttää suoraan kuka on tehnyt mitäkin työtä tiedostossa eli kuka on kirjoittanut minkä rivin. Aluksi komento ei näyttänyt minulle mitään, mutta googlasin ja löysin hyvän selityksen.
Piti laittaa tiedoston nimi komennon perään niin komento toimi.
Lähde: [Git Blame Explained with Examples](https://www.freecodecamp.org/news/git-blame-explained-with-examples/) Luettu 19.4.2022


## c) Huppis!

Tee tyhmä muutos gittiin, älä tee commit:tia. Tuhoa huonot muutokset ‘git reset --hard’. Huomaa, että tässä toiminnossa ei ole peruutusnappia.

Aloitin tekemällä git varaston kansioon tiedoston 

		$ micro Huppis.md

sen jälkeen tein git add. Tämän jälkeen tuhosin huonot muutokset komennolla:

		$ git reset --hard

Komennon jälkeen sain viestin "HEAD is now at..." eli viimeinen muutos oli tuon reset komennon jälkeen viimeisin commit ja tyhmä muutos oli poistettu.

## d) Formula

Tee uusi salt-tila (formula, moduli, infraa koodina). (Eli uusi tiedosto esim. /srv/salt/terontila/init.sls). Voit tehdä ihan yksinkertaisen parin funktion (pkg, file...) tilan, tai edistyneemmin asentaa ja konfiguroida minkä vain uuden ohjelman: demonin, työpöytäohjelman tai komentokehotteesta toimivan ohjelman. Käytä tarvittaessa ‘find -printf “%T+ %p\n”|sort’ löytääksesi uudet asetustiedostot.

Aloitin tekemällä uuden kansion /srv/salt/vscode ja tein sinne init tiedoston

		$ sudoedit /srv/salt/vscode/init.sls

Jonne tein pkg tilan, koska halusin asentaa Visual Studio Code -ohjelman.

code:
  pkg.installed

Sen jälkeen kommenolla:

		$ sudo salt '*' state.apply vscode 

Ajoin luomani uuden salt- moduulin ja sain onnistuneen palautteen, Succeeded: 1 ja changed=1. Ajoin moduulin vielä kerran ja muutoksia ei enää tullut joten komento on idempotentti.

![image](https://user-images.githubusercontent.com/60943507/164013843-ec9c3c0e-71ef-4162-a5f6-94ecca6ebd14.png)
Varmistin vielä, että ohjelma oli oikeasti asennettu.

*Ennen kuin tein init.sls tiedoston seurasin googlesta löytmämiäni ohjeita miten vscode asennetaan (Microsoft GPG key jne)
Lähde: [How to Install Visual Studio Code on Ubuntu 20.04](https://linuxize.com/post/how-to-install-visual-studio-code-on-ubuntu-20-04/) Luettu: 19.4.2022


## Lähteet:

https://terokarvinen.com/2021/configuration-management-systems-2022-spring/ Luettu 19.4.2022
[MarkDown-artikkeli](https://commonmark.org/help/)
[Git Blame Explained with Examples](https://www.freecodecamp.org/news/git-blame-explained-with-examples/) Luettu 19.4.2022
[How to Install Visual Studio Code on Ubuntu 20.04](https://linuxize.com/post/how-to-install-visual-studio-code-on-ubuntu-20-04/) Luettu: 19.4.2022

Tätä dokumenttia saa kopioida ja muokata GNU General Public License (versio 2 tai uudempi) mukaisesti. http://www.gnu.org/licenses/gpl.html

Pohjana Tero Karvisen Palvelinten Hallinta kurssi, Kevät 2022 https://terokarvinen.com/2021/configuration-management-systems-2022-spring/
