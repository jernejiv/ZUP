# Diagram poteka za zakon o upravnem sporu – spremno besedilo.

Sodna kontrola zakonistosti, gre za sodni spor v pristojnosti sodišč. Mora biti posamičen, se pravi posegati v položaj posameznika. Bistvo je, da gre za enakopraven položaj stranke in organa.

Tožbeni razlogi, ki jih je potrebno navesti č26:
- kršitev materialnega prava/predpisa
- kršitev pravil postopka
- nepravilna ali nepopolna ugotovitev dejanskega stanja
- ničnosti razlogi

Pri vlogi tožbe je potrebno navesti zahteve ali predloge, na kaj se tožba nanaša:
- Odprava upravnega akta
- ugotovitev nezakonitosti akta ( ugotovitvena tožba)
- tožba zaradi molka organa
- sprememba akta – spor polne juristikcije
- ugotovitev nezakonitosti dejanj človekovih pravic – prepoved nadaljevanja in odprava posledic

Nekaj pomembnih dejstev pri tožbah:
- rok za tožbo začne teči z vročitvijo upravnega akta č23 - kaj pa dokočni upravni akt
- Tožba ne zadrži izvršitve, lahko se izda začasna odredba, če se lahko povzroči težko popravljiva škoda č32. Lahko pa izda začasno odredbo
- Tožba ni dovoljena (nedopustna), če ni vložena pritožba in hkrati je bila možnost tožbe, ali gre za akt izvršljive oblasti utemeljene na politični diskresiji ali pa akt zakonodajne / sodne oblasti oblasti iz naslova ustave
- vlogo za revizijo lahko oddajo osebe, ki imajo pravniški državni izpit - odvetnik
- tožnik lahko umakne tožbo č34

Diagram poteka v grobem prikazuje kako poteka postopek upravnega spora. Prikazuje kaj so vhodi, kdo so stranke, kateri dokumenti so potrebni za odločanje. V grobem prikazuje osnovne aktivnosti in odločitve, ki jih mora sprejeti pristojno sodišče in po kateri veji lahko pridemo do konca ali rezultata/sodbe.

```mermaid
flowchart TD
ZAC[Začetek: Dokončni Upravni akt č2, odločba ali končni sklep]
SDKCP[Storjeno dejanje, ki krši človekove pravice]
ZAC --> |Tožnik vloži| TOZBA["**ToŽba**: tožnik, toženec, upravni akt, ki se spodpija, razlaga zakaj, predlog kako in zahteve, priloge ..."]
SDKCP --> TOZBA
TOZBA --> |Odloča pristojno sodišče| TP{popolna<BR>razumljiva}
TP --> |NE| C2[poziv o dopolnitvi ali odpravi pomanklivosti č31]
C2 --> C3{OK}
C3 -->|NE| C4[sklep o zavrženju, konec pred odločanje]
TP --> |DA| D
C3 -->|DA| D[Tožba sprejena, preverjanje formalnih pogojev in vsebinska dopustnost, č27]
D --> V1{preizkus<BR> tožbe č36}
V1 -->|Tožba vsebinsko zavržena| C4
V1 -->|Rok 30 dni je potekel| C4            
V1 -->|bistvene pomanljivosti č37| SODL4[sodba o odpravi odločbe, konec postopka]
SODL4 --> VRO
V1 --> |Nedopustnost upravnega spora č6| NUS[Zakonodajne sodne in izvršilne oblasti ali ni bilo pritožbe]
NUS --> C4
V1 -->|Tožba sprejeta| G[Pošiljanje tožbe tožencu]
G --> H[Odgovor toženca v 30 dneh]
H --> |več kot 20 upravnih aktov| VP[vzočni postopek]
H --> PV{predhodno<BR> vprašanje <BR> pristojnosti č11}
PV --> |DA| PP[prekinitev postopka]
PV --> |NE| I
PP --> I
H --> I[Pripravljalni postopek]
I --> POR[Poravava, kadarkoli do izdaje sodbe in končanje postopka z zapisnikom]
I --> |Zagotovljena kontradiktornost| J[Glavna obravnava, imamo zapisnik]
J --> POR
I --> |Dejansko stanje ni sporno č59| SS[sojenje na seji]
J --> K{Upravno<BR> Sodišče<BR> odloča}
SS --> K
K --> |Spor zakonitosti| SZ{utemeljena}
SZ --> |DA| SOD1["**Sodba**: ugodi in odpravi upravni akt č64"]
SOD1 --> |lahko odloči| PND[Prepoved nadaljevanja dejan č66j in odškodninski zahtevek]
VROS[Vročitev Sklepa]
K --> |ničnost upravnega akta| S7[Sklep o ničnosti]
S7 --> VROS
PND -->VRO
SZ --> |NE| SOD3[**Sodba**:  zavrne č63]
SOD3 --> VRO
K --> |Spor polne juristikcije meritorno| SOD2["**Sodba**: upravni akt odpravi in odloči o stvari č65"]
SOD2 --> VRO

VRO[Vročitev sodbe]
VRO --> M{Rok za pritožbo<BR> 15 dni}
%% Drugi del
M -->|Pritožba vložena| N[Postopek pred Vrhovnim sodiščem]
M -->|Ni dovoljena| PRIND[spor iz zakonitosti, ni bistvenih kršitev, ni zmotne uporabe materialnega prava li ugotovitve dejanskega stanja]
PRIND--> PS
M -->|Pritožba ni vložena| PS[Pravnomočnost sodbe]
N --> OVS[Odločitev Vrhovnega sodišča pod pogojem, da je spremenjen upravni akt in meritorna odločitev ali človekove pravice]
OVS --> PRIZ{Pritožba<BR> zavrnjena}
PRIZ --> |DA| PS
PRIZ --> |NE| R[Sodba razveljavljena, v primeru spora zakonitosti]
R --> S[Vrnitve zadeve na prvo stopnjo]
%% S --> J
PS --> IZV[Izvršba sodbe]
%% POR --> KON

IZV --> KON[Konec postopka]
PS --> VD{dodatne<BR> možnosti}
VD -->|Revizija vložena v 30 dneh| W[Postopek revizije]
W --> X{Odločitev<BR> o reviziji}
X --> |Revizija zavrnjena č85| IZV
X --> |Revizija ugodena| S
VD -->|obnova postopka osebe z izpitom č96| OP[Obnova postopka]
OP --> |zavrženo| IZV

ZAC@{shape: doc}
TOZBA@{shape: doc}
C4@{shape: doc}
SOD1@{shape: doc}
SOD2@{shape: doc}
SOD3@{shape: doc}
S7@{shape: doc}
```

## Razredni diagram ZUS
    
```mermaid  
classDiagram
class UpravniAkt {
    +String naziv
    +Date datumIzdaje
    +Organ izdalOrgan
    +Boolean jeDokončan
    +Boolean jeNičen
    +odpravi()
    +ugotoviNezakonitost()
}

class Sodišče {
    +String naziv
    +String sedež
    +List~Senat~ senati
    +List~Sodnik~ sodniki
    +odločiOTožbi(Tožba)
    +izdaSodbo()
    +izdaSklep()
}

class UpravnoSodišče {
    +krajevnaPristojsnot:[Celje, Nova Gorica, Maribor]
    +odločiNaPrviStopnji(Tožba)
    +določiPristojnostGledeNaTožnika()
}

class VrhovnoSodišče {
    +odločiOPritožbi(Pritožba)
    +odločiOReviziji(Revizija)
}

class Senat {
    +List~Sodnik~ člani
    +Sodnik predsednik
    +odločiOZadevi()
}

class Sodnik {
    +String ime
    +String priimek
    +Boolean jePredsednikSenata
    +odločiPoSvojiPristojnosti()
}

class Tožba {
    +String tožnik
    +String toženec
    +UpravniAkt izpodbijanAkt
    +Date datumVložitve
    +String razlog
    +String predlogAliZahteva
    +String storjenoDejanje()
    +Boolean jeSprejeta()
    +preveriFormalnePogoje()
}

class Pritožba {
    +String pritožnik
    +Sodba izpodbijanaSodba
    +Date datumVložitve
    +String razlog
    +String zahteva
    +preveriRok()
}

class Revizija {
    +String revident
    +Sodba izpodbijanaSodba
    +Date datumVložitve
    +String razlog
    +preveriRok()
}

class Sodba {
    +String izrek
    +String obrazložitev
    +Date datumIzdaje
    +Boolean jePravnomočna
    +razglasi()
}

class Sklep {
    +String vsebina
    +Date datumIzdaje
    +izvrši()
}

class Stranka {
    <<abstract>>
    +String ime
    +String naslov
    +String vloga
    +vložiTožbo(UpravniAkt)
}

class Tožnik {
    +posameznik: Stranka
    +vložiTožbo(UpravniAkt)
}

class Toženec {
    +pravna oseba / prizadeta oseba / organ
    +odgovoriNaTožbo(Tožba)
}

class ZastopnikJavnegaInteresa {
    +vložiTožbo(UpravniAkt)
}

%% Odnosi
UpravniAkt "1" -- "1" Organ : izdal
Sodišče <|-- UpravnoSodišče
Sodišče <|-- VrhovnoSodišče
VrhovnoSodišče "1" -- "*" UpravnoSodišče : nadzira
Sodišče "1" *-- "*" Senat : vsebuje
Senat "1" *-- "*" Sodnik : sestavljen iz
Sodnik "1" -- "1" Senat : predsednik
Sodišče "1" -- "*" Tožba : obravnava
Sodišče "1" -- "*" Sodba : izda
Sodišče "1" -- "*" Sklep : izda
Tožba "1" -- "1" UpravniAkt : izpodbija
Tožba "1" -- "1" Tožnik : vložil
Tožba "1" -- "1" Toženec : naslovljen na
Tožba "1" -- "*" Pritožba : lahko vložena
Sodba "1" -- "*" Pritožba : izpodbijana
Sodba "1" -- "*" Revizija : izpodbijana
Stranka <|-- Tožnik
Stranka <|-- Toženec
Tožnik <|-- ZastopnikJavnegaInteresa

style Sodba stroke:#8eebee
%% linkStyle 4 stroke:red;
```
