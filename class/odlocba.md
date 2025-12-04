## Odločba razredni diagram

```mermaid
---
config:
  layout: elk
---
classDiagram
class Odločba {
    +št: String
    +datum: Datum
    +uvod: Uvod
    +naziv: String
    +izrek: Izrek : dispoziv
    +obrazložitev: Obrazložitev
    +pouk: PoukPravnegaSredstva
    +podpis: String
    +status: StatusOdločba
    +načinUvedbe: NačinUvedbe
    +vročitev()
    +pritožba()
    +tožba()
}

class Uvod {
    +imeOrgana: String
    +pristojnost: String
    +načinUvedbe: NačinUvedbe
    +stranka: String
    +zadeva: String
}

class Izrek~Dispoziv~ {
    +predmetPostopka: String
    +zahtevki: String[]
    +stroški: String
    %% optional
    -?pogoji: String[]
    -?rokIzvršitve: Date
    -?izvršitevUčinkujeTakoj: String
}

class Obrazložitev {
    +zahtevkiStrank: String
    +dejanskoStanje: String
    +dokazi: String[]
    +razlogi: String[]
    +predpisi: String[]
}

class PoukPravnegaSredstva {
    +pravnoSredstvo: (pritožba)
    +naKajJeMožno: String
    +rok: Date
    +organ: String
    +taksa
    +alijepritožbaMožna()
}

class StatusOdločba {
    <<enumeration>>
    + Izdana
    + Dokončna
    + Pravnomočna
    + Izvršljiva
}

class NačinUvedbe {
    <<enumeration>>
    + naZahtevoStranke
    + UradnaDolžnost
}

class Pritozba{
    +razlog: String
}

class Sklep~Odločba~ {
    +uvod: Uvod
    +naziv: String
    +izrek: Izrek
    +podpis: String
    +Ustni(): bool
    +Koncni(): bool
    +Ivršljiv(): bool
    +pritozbaMozna: privzeto NE
    +PriotbaZadrziIzvrsitev(): privzeto DA
}


Odločba "1" *-- "1" Uvod: mora imeti
Odločba "1" *-- "1" Izrek: mora imeti
Odločba "1" *-- "1" Obrazložitev
Odločba "1" *-- "1" PoukPravnegaSredstva
Odločba "1" *-- "0" Pritozba : privzeto ima možnost
Odločba "1" *-- "1" StatusOdločba
Odločba "1" *-- "1" NačinUvedbe

Sklep "1" *-- "1" Uvod: mora imeti
Sklep "1" *-- "1" Izrek: mora imeti
Sklep "1" *-- "0" Obrazložitev: pod pogojem, pritožba možna
Sklep "1" *-- "0" PoukPravnegaSredstva: pod pogojem, pritožba možna
Sklep "1" *-- "0" Pritozba : V zakonu zapisana možnost

```

