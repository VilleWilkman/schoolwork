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

git config --global user.email 'tonystudent@example.com'

git config --global user.name 'Tony Student'

Luonnollisesti kyseisiin kohtiin syötetään siis omat tietosi. Seuraavaksi sain Git-tilini haltuun komennolla:

git clone -url-omasta-gitistäsi-

Näin kloonasin git-tilini koneelleni ja pääsin siihen käsiksi. Git-tilini kansiossa "schoolwork", loin uuden tiedoston nimeltä "harjoitus3.md" Markdown:lla komennolla: 

sudo nano harjoitus3.md

ja kokeilin toimiiko synkronointi Linuxini ja Git-tilini välillä seuraavalla komennolla:

git add . && git commit; git pull && git push

Annoin muokkaukselleni nimen (tässä tapauksessa uuden tieston luonti) "Just modified" ja syötin käyttäjänimeni sekä salasanani ja sinnehän tuo tiedosto ponnahti.
