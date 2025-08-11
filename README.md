# Geemufooramu <sub><sub>(GameForum, japanese)

(Tietokannat ja web-ohjelmointi kurssityö)

Sovellus ei ainakaan vielä ole testattavissa fly.io osoitteessa

Pelikeskustelusovellus <br/>
Sovelluksessa näkyy keskustelualueita, joista jokaisella on tietty aihe (tietty peli, softa yms.). Alueilla on keskusteluketjuja, jotka muodostuvat viesteistä. Jokainen käyttäjä on peruskäyttäjä tai ylläpitäjä.

Sovelluksen ominaisuuksia:

- [x] Käyttäjä voi kirjautua sisään ja ulos sekä luoda uuden tunnuksen. <br/> 
- [x] Käyttäjä näkee sovelluksen etusivulla listan alueista sekä jokaisen alueen ketjujen ja viestien määrän ja viimeksi lähetetyn viestin ajankohdan. <br/>
- [x] Käyttäjä voi luoda alueelle uuden ketjun antamalla ketjun otsikon ja aloitusviestin sisällön. <br/>
- [x] Käyttäjä voi kirjoittaa uuden viestin olemassa olevaan ketjuun. <br/>
- [x] Käyttäjä voi muokata lähettämänsä viestin sisältöä. Käyttäjä voi myös poistaa viestin. <br/>
- [] Käyttäjä voi etsiä kaikki viestit, joiden osana on annettu sana. <br/>
- [x] Ylläpitäjä voi poistaa muiden viestejä. <br/>
- [] Ylläpitäjä voi luoda salaisen alueen ja määrittää, keillä käyttäjillä on pääsy alueelle. <br/>
- [x] Käyttäjä voi muokata profiiliaan, ja katsella muiden profiileja


## ASENNUS

Kloonaa tämä repositorio omalle koneellesi.
```
$ git clone https://github.com/JoonaPietarinen/Geemufooramu
$ cd GeemuFooramu
```
siirry sen juurikansioon. Luo kansioon .env-tiedosto ja määritä sen sisältö seuraavanlaiseksi:
```
DATABASE_URL=postgresql://<tietokannan-paikallinen-osoite>
SECRET_KEY=<salainen-avain>
```
Seuraavaksi aktivoi virtuaaliympäristö ja asenna sovelluksen riippuvuudet komennoilla
```
$ python3 -m venv venv
$ source venv/bin/activate
$ pip install -r ./requirements.txt
```
Luo tietokanta ja määritä tietokannan skeema komennolla
```
$ psql
user=# CREATE DATABASE <new-db-name>;
user=# \q
$ psql -d <new-db-name> < schema.sql
```
Tämän jälkeen luo testi käyttäjät sekä alueet
```
$ psql -d <new-db-name> < test1.sql
```
Nyt voit käynnistää sovelluksen komennolla
```
$ flask run
```

## KÄYTTÄJIÄ
Testi käyttäjiä ovat:
| username | password | role  |
|----------|----------|-------|
| admin    | admin    | admin | 
| testuser | password | user  |
