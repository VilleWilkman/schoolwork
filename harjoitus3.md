# Harjoitustehtävä 3

## C) Näytä omalla salt-varastollasi esimerkit komennoista ”git log”, ”git diff”, ”git blame”. Selitä tulokset.

### Gitin asennus ja valmistelu. 

Lähdin tekemään harjoitustehtäväkokonaisuutta ensin kokeilemalla, saanko yhteyden Masterilla Orjiin. Kokeilin seuraavia komentoja:

```
sudo salt '*' cmd.run 'hostname -I'

sudo salt '*' cmd.run 'whoami'
```

Esiin putkahtivat orjien IP-osoitteet sekä tieto, että Master on Root. Kaikki siis alustavasti toimi niinkuin pitikin.

Olin jo aikaisemmin luonut itselleni tilin github.com:in, joten lähdin kokeilemaan pääsisinkö sinne sisälle Linuxini kautta. Asensin gitin komennolla:

```
sudo apt-get install -y git
```

Seuraavaksi etenin kurssimateriaalien mukaan (http://terokarvinen.com/2016/publish-your-project-with-github), jossa käskettiin syöttämään tiedoton käyttäjän emailista ja käyttäjän nimestä seuraavilla komennoilla:

```
git config --global user.email 'tonystudent@example.com'

git config --global user.name 'Tony Student'
```

Luonnollisesti kyseisiin kohtiin syötetään siis omat tietosi. Seuraavaksi sain Git-tilini haltuun komennolla:

```
git clone -url-omasta-gitistäsi-
```

Näin kloonasin git-tilini koneelleni ja pääsin siihen käsiksi. Git-tilini kansiossa "schoolwork", loin uuden tiedoston nimeltä "harjoitus3.md" Markdown:lla komennolla: 

```
sudo nano harjoitus3.md
```

ja kokeilin toimiiko synkronointi Linuxini ja Git-tilini välillä seuraavalla komennolla:

```
git add . && git commit; git pull && git push
```

Annoin muokkaukselleni nimen (tässä tapauksessa uuden tieston luonti) "Just modified" ja syötin käyttäjänimeni sekä salasanani ja sinnehän tuo tiedosto ponnahti.



### Sitten itse varsinaiseen tehtävään eli saltilla luomaan tila, jolla annetaan komentoja

Loin github.com:in uuden kansion nimellä "saltstates". Seuraavaksi siirryin Linuxillani "/srv/salt" -hakemistoon, johon halusin linkittää tuon luomani "saltstates" -kansion. Tein seuraavat komennot siis "/srv/salt" -hakemistossa:

```
git config --global user.email 'omaemail'

git config --global user.name 'omakäyttäjänimi'
```

Ja näin sain näkyviin "saltstates" -kansioni.

Tämän jälkeen loin kyseiseen kansioon tiedoston "testitila.md" ja yritin työntää sitä gittiin, mutta oikeudet eivät riittäneet edes sudo:lla. Ratkaisin ongelman antamalla oikeudet itselleni seuraavalla komennolla:
```
chown -R youruser:yourgroup .git/
```
Linkki vielä: https://stackoverflow.com/questions/13195814/trying-to-git-pull-with-error-cannot-open-git-fetch-head-permission-denied

Tämän jälkeen synkronointi gitin kanssa onnistui! Tosin, en ole aivan varma mitä tein, mutta teinpähän kuitenkin, koska testiympäristössä ollaan.
