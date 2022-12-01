# h5-windows
palvelinten hallinta s22 vaihtoehtoiset järjestelmät

ALoitin lataamalla tunnilla salt-minionin Windowsille. Windows osoittautui yllättävän hankalaksi, sillä olen aina käyttänyt vain linuxia, joten esim. komennot ei tuntunut toimivan samalla tavalla. Latauksen jälkeen avasin windowsin powershellin järjestelmänvalvojana (run as administrator).

https://repo.saltproject.io/salt/py3/windows/3005.1-1/salt-3005.1-1-windows-amd64.exe latauslinkki tiedostoon.

![windows](https://user-images.githubusercontent.com/118457367/204983420-7cdf1aa6-0c15-47a0-a63e-202bbe3a66d0.jpg)

Testailin aluksi perus komentoja (ls, pwd ...), ja yritin tutustua windowsiin. 

Tämän jälkeen ongelmaksi muodostui se, etten muka ollut "administrator" omalla windows käyttäjällä, vaikka olen. En siis saanut tiedostoa millään auki oikein, joten en löytänyt salttia koneelta. 

Kuitenkin yritysten jälkeen onnistuin etenemään.

Ensin allaolevalla komennolla siirryin omaan latauskansiooni: 

![komento1](https://user-images.githubusercontent.com/118457367/204985725-689f6a3e-c76f-4b43-a6c3-0f320855cefe.jpg)

Josta löysin ladatun tiedoston, jonka avasin allaolevalla komennolla: 

![komento2](https://user-images.githubusercontent.com/118457367/204985845-81279263-0e3c-4e68-9b27-9d226b8e9daa.jpg)

Tämän jälkeen tiedosto avautui, ja pääsin asettamaan esimerkiksi masterin ja minionin nimet, jonka jälkeen tiedosto lähti latautumaan. 

