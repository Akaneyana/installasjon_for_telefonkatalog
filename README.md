# installasjon_for_telefonkatalog

## Instalasjon av Ubuntu

1. Laste ned et program som heter [Raspberry Pi Imager](https://www.raspberrypi.com/software/) på en enhet som har en micro sd kort leser. 

2. Ta micro sd kortet ut fra Raspberry Pi og set den in inni enheten som har micro sd kort leser.

3. Åpne Raspberry Pi Imager og velg din Raspberry Pi versjon i "CHOOSE DEVICE". 

4. Nå Velger "CHOOSE OS" og scroll ned til du finner "Other general-purpose OS" og klikk på den. Nå skal du trykke på Ubuntu og ta nyeste versjon av Ubuntu (Ofte den øverste)

5.  Trykk på "CHOOSE STORAGE" og velg sd kortet som du har pyttet inni enheten. Og last det ned.

6. Etter den er ferdig å installere put micro sd kortet tilbake inni i Raspberry pi.

## Oppsett av Ubuntu

1. I "System Configuration" Velger du et språk du er komfortabel med enten dette er Norsk eller Engelsk.

2. I "Keyboard Layout" skjermen velger du et tastaturoppsett som du er komfortabel, som er Norsk en stor del av tiden.

3. Nå kan du koble til Internet på Raspberry Pi-en din. Du kan enten gjøre det nå eller etter Ubuntu Oppsetten.

4. Nå for du velge hvilke Land du er fra.

5. I neste skjermen kan du skrive navnet ditt og hva du vil kalle Raspberry pi-en, sammen med passord.

## Oppdatering av Ubuntu

Siden vi har lastet ned Ubuntu må vi også oppdatere selve enheten. Hvordan vi gjør dette er å gjøre denne shortcuten under til å åpne command prompt.
``Ctrl + Alt + T``

Nå er det er linjer vi må skrive til å opdatere Rasperry Pi-en og det er de linjene under

```bash 
sudo apt install 

sudo apt upgrade 
```

## Installering av programmer

1. Brannmur med hjelp av UFW

```bash 
sudo apt install ufw (installerer UFW )

sudo ufw enable (slår på brannmur ved starten av maskinen)

sudo ufw allow ssh (lar SSH-tilkoblinger gå gjennom brannmuren)
```

2. Aktivere ssh 

```bash 
sudo apt install openssh-server (installerer SSH-server)

sudo systemctl enable ssh (slår på SSH ved starten av maskinen)

sudo systemctl start ssh (starter opp SSH)
```

3. Finne Ip adressen til maskinen

```bash
ip a 
```

Hvis du er koblet via trådløst nettverk vil ip vises ved wlan0.

4. Styre Raspberry-pi med SSH
```bash
ssh brukernavn@ip
```
Med SSH kan vi styre Pi-en med laptopen din via cmd. Skriv in brukernavnet i Pi-en i 'brukernavn' og ip-adressen til Pi-en i 'ip'

5. Installer Python, Git og MariaDB

```bash
sudo apt install python3-pip

sudo apt install git

sudo apt install mariadb-server

sudo mysql_secure_installation
```

## Lag bruker og gi rettigheter i MariaDB

```bash
sudo mariadb -u root (til å login i mariadb med admin bruker)
```

```sql
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password'; (skriv egen username i 'username' felte sammen med password)

GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' IDENTIFIED BY 'password'; (gir høyeste Rettigheter til den brukeren i MariaDB)

FLUSH PRIVILEGES; (oppdaterer rettighetene)
```