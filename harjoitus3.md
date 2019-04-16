### Gitin asennus ja valmistelu. 

Lähdin tekemään harjoitustehtäväkokonaisuutta ensin kokeilemalla, saanko yhteyden Masterilla Orjiin. Kokeilin seuraavia komentoja:

sudo salt '*' cmd.run 'hostname -I'
sudo salt '*' cmd.run 'whoami'

Esiin putkahtivat orjien IP-osoitteet sekä tieto, että Master on Root. Kaikki siis alustavasti toimi niinkuin pitikin.
