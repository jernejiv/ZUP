## Stranka v postopku razredni diagram

```mermaid
classDiagram
class Oseba {
    +id: String
}

class UdelezenecPostopka{
}

class FizičnaOseba{
    +ime: String
    +priimek: String
    +Naslov: String
}

class pravnaOseba{
    +Naziv: String
    +naslov: String
    +direktor: String
}

PravnaOseba --> ZakonitiZastopnik : ima po zakonu č48

Oseba <|-- FizičnaOseba
Oseba <|-- pravnaOseba

class StranskiUdelezenec{
    +ime: String
    +priimek: String
    +Naslov: String
}

class Stranka{
  +opravlja dejanja v postopku()
}

UdelezenecPostopka "1" -- "*"  Stranka

Stranka <-- Oseba : Procesno sposobna in legitimna

Oseba --> StranskiUdelezenec : ima pravno korist in procesno sposobnost
Stranka <|-- StranskiUdelezenec : ima enake pravice

class ZakonitiZastopnik{
}

Stranka --> "1" ZakonitiZastopnik: ima po zakonu, če ni procesno sposeobna ... č47
Stranka <-- "1" ZakonitiZastopnik: opravlja dejanja kot
Oseba --> ZakonitiZastopnik: če ni procesno sposobna


class Pooblaščenec{
  +pisno pooblastilo
  +za katera dejanja postopka()
}

Stranka <-- "*" Pooblaščenec: ima pooblastilo
FizičnaOseba --  Pooblaščenec: je lahko
PravnaOseba --  Pooblaščenec: odvetniška družba ...

class ZačasniZastopnik{
  +imenuje uradna oseba()
}

ZakonitiZastopnik <|-- ZačasniZastopnik : ima enake pravice
%% UradnaOseba --> ZačasniZastopnik : imenuje

class PredstavnikSkupine{
 +izbraniPredstavnik: FizičnaOseba
}
class Skupina{
 + stranka:Stranka[]
}
Skupina --> PredstavnikSkupine : ima
PredstavnikSkupine --> Stranka : sodeluje kot

class Organ{
  + naziv: String
  + sedež: String
  + predstojnik: FizičnaOseba
  + zaposleni: FizičnaOseba[]
  + pridobi pristojnost()
  + določi uradno osebo()
}

class UradnaOseba{
  +izbrana za Vodenje:FizičnaOseba
  +izbrana za Odločanje:FizičnaOseba
}

PooblaščeniZaposlen <-- FizičnaOseba
UradnaOseba <|-- PooblaščeniZaposlen
UradnaOseba <|-- Predstojnik
UradnaOseba <|-- Inšpektor
PooblaščeniZaposlen <-- Predstojnik : pooblastilo odločba
Predstojnik --> Organ : vodi

UradnaOseba <-- Organ : določi

UradnaOseba --> "1" UdelezenecPostopka : vodi postopek
UradnaOseba --> "1" UdelezenecPostopka : odloča v postopku

FizičnaOseba --> StrokovniPomočnik : ne zastopa stranke
```
