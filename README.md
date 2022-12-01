# h5-windows
palvelinten hallinta s22 vaihtoehtoiset järjestelmät

ALoitin lataamalla tunnilla salt-minionin Windowsille. Windows osoittautui yllättävän hankalaksi, sillä olen aina käyttänyt vain linuxia, joten esim. komennot ei tuntunut toimivan samalla tavalla. Latauksen jälkeen avasin windowsin powershellin järjestelmänvalvojana (run as administrator).

https://repo.saltproject.io/salt/py3/windows/3005.1-1/salt-3005.1-1-windows-amd64.exe latauslinkki tiedostoon.

![windows](https://user-images.githubusercontent.com/118457367/204983420-7cdf1aa6-0c15-47a0-a63e-202bbe3a66d0.jpg)

Testailin aluksi perus komentoja (ls, pwd ...), ja yritin tutustua windowsiin. 

Tämän jälkeen ongelmaksi muodostui se, etten muka ollut "administrator" omalla windows käyttäjällä, vaikka olen. En siis saanut tiedostoa millään auki oikein, joten en löytänyt salttia koneelta. 

Kuitenkin yritysten jälkeen onnistuin etenemään.

 **tehtävä a) Hello Window Salt! Tee Windowsille SLS-tiedostoon Salt-tila, joka tekee tiedoston nimeltä "suolaikkuna.txt".**

Ensin allaolevalla komennolla siirryin omaan latauskansiooni: 

![komento1](https://user-images.githubusercontent.com/118457367/204985725-689f6a3e-c76f-4b43-a6c3-0f320855cefe.jpg)

Josta löysin ladatun tiedoston, jonka avasin allaolevalla komennolla: 

![komento2](https://user-images.githubusercontent.com/118457367/204985845-81279263-0e3c-4e68-9b27-9d226b8e9daa.jpg)

Tämän jälkeen tiedosto avautui, ja pääsin asettamaan esimerkiksi masterin ja minionin nimet, jonka jälkeen tiedosto lähti latautumaan. 

Sen jälkeen siirryin salt kansioon (cd C:\salt\srv), jossa loin notepadiin suolaikkuna.txt sekä init.sls tiedoston, jotka näyttivät tältä: 

![suolaikkunajainit](https://user-images.githubusercontent.com/118457367/205048461-2b925585-fd16-440b-aa93-9e7d71473b9e.jpg)

Näiden luomisen jälkeen kokeilen toimiiko:

![windowssucceed2](https://user-images.githubusercontent.com/118457367/205048642-cc99c267-c8ff-4a26-986d-fc6ea730f7b5.jpg)

Toimi. 

**tehtävä b) Ei vihkoa, ei kynää. Kerää Windows-koneen tekniset tiedot tekstitiedostoon. Vapaaehtoinen bonus: Saatko tiedot tallennettua myös json-muodossa?**

Lähden etenemään sillä taktiikalla, että kerään koneesta tietoja grains.items -komennolla, jotka siirrän tekstitiedostoon.

Eli periaatteessa laitoin vain allaolevan komennon:

![tiedot](https://user-images.githubusercontent.com/118457367/205051367-2091c547-e78a-4461-bcff-8fb8d08a15bd.jpg)

Jonka jälkeen tsekkasin vielä cat tiedotkoneesta.txt -komennolla, että onnistui. 

Yritin myös katsella tuota bonusta aka json -tiedostona koneen tietojen tallentamista, mutta se ei oikein onnistunut, sillä en tiennyt mistä aloittaa tekemään. 

**c) Kop kop. Onko TCP-portti auki vai kiinni? Näytä esimerkit portin kokeilusta Linuxilla ja Windowsilla. Näytä kummallakin käyttöjärjestelmällä ainakin yksi avoin ja yksi suljettu portti. (Kokeile tätä vain omaan koneeseesi. Vieraiden koneiden ja verkkojen porttiskannaaminen on kiellettyä. Yksittäisen portin testaavat komennot ovat suositeltavia, esim. nc, tnc)**

Kokeilin komennolla $ netstat -an mitä portteja löytyy, ja niitähän löytyi jonkin verran:

![tcpportit](https://user-images.githubusercontent.com/118457367/205054014-103fa1ef-81f0-4418-8a21-e30b8f1b24f3.jpg)

Tuloksena oli portteja jotka olivat tilassa: listening, established ja time_wait. Eli minulla oli portteja (listening), joihin oli muodostettu yhteys, established - eli portteja joihin voisin muodostaa yhteyden/avoinna olevat sekä time_wait portteja, joka tarkoittaa ettei kummallakaan osapuolella ole dataa lähetettävänä, mutta kummatkin voisi silti vastaanottaa dataa. 
