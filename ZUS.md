# Diagram poteka za zakon o upravnem sporu – spremno besedilo.

Sodna kontrola zakonistosti, gre za sodni spor v pristojnosti sodišč. Mora biti posamičen, se pravi posegati v položaj posameznika. Bistvo je, da gre za enakopraven položaj stranke in organa.

Tožbeni razlogi, ki jih je potrebno navesti:
- kršitev materialnega prava
- nepravilna ali nepopolna ugotovitev dejanskega stanja
- kršitev pravil postopka
- ničnosti razlogi

Pri vlogi tožbe je potrebno navesti zahteve, na kaj se tožba nanaša:
- Odprava akta
- ugotovitev nezakonitosti akta
- molk organa
- sprememba akta – spor polne juristikcije
- ugotovitev nezakonitosti dejanj – prepoved nadaljevanja in odprava posledic

Nekaj pomembnih dejstev pri tožbah:
- Tožba ne zadrži izvršitve, lahko se izda začasna odredba, če se lahko povzroči težko popravljiva škoda.
- Tožba ni dovoljena (nedopustna), če ni vložena pritožba in hkrati je bila možnost tožbe, ali gre za akt izvršljive oblasti utemeljene na politični diskresiji ali pa akt zakonodajne / sodne oblasti oblasti iz naslova ustave
- vlogo za revizijo lahko oddajo osebe, ki imajo pravniški državni izpit - odvetnik

Diagram poteka v grobem prikazuje kako poteka postopek upravnega spora. Prikazuje kaj so vhodi, kdo so stranke, kateri dokumenti so potrebni za odločanje. V grobem prikazuje osnovne aktivnosti in odločitve, ki jih mora sprejeti pristojno sodišče in po kateri veji lahko pridemo do konca ali rezultata/sodbe.

```mermaid
flowchart TD
    ZAC[Začetek: Dokončni Upravni akt č2, odločba ali končni sklep]
    SDKCP[Storjeno dejanje, ki irši šlovekove pravice]
    ZAC --> |Tožnik vloži| TOZBA["**ToŽba**: tožnik, toženec, upravni akt, ki se spodpija, razlaga zakaj, predlog kako in zahteve, priloge ..."]
    SDKCP --> TOZBA
    TOZBA --> |Odloča pristojno sodišče| TP{popolna<BR>razumljiva}
    TP --> |NE| C2[poziv o dopolnitvi ali odpravi pomanklivosti č31]
        C2 --> C3{OK}
        C3 -->|NE| C4[sklep o zavrženju]
    TP --> |DA| D
        C3 -->|DA Tožba vložena| D[Preverjanje formalnih pogojev in vsebinska dopustnost, č27]
        D --> V1{preizkus<BR> tožbe č36}
        V1 -->|Tožba zavržena| F[Konec postopka - sklep]
            F --> KON
        V1 -->|Rok 30 dni je potekel| C4            
        V1 -->|bistvene pomanljivosti č37| F1[sodba o odpravi - konec]
            F1 --> KON
        V1 --> |Nedopustnost upravnega spora č6| NUS[Zakonodajne sodne in izvršilne oblasti ali ni bilo pritožbe]
            NUS --> C4
        V1 -->|Tožba sprejeta| G[Pošiljanje tožbe tožencu]
            G --> H[Odgovor toženca v 30 dneh]
    H --> |več kot 20 upravnih aktov| VP[vzočni postopek]
    VP --> I
    H --> PV{predhodno<BR> vprašanje <BR> pristojnosti č11}
    PV --> |DA| PP[prekinitev postopka]
    H --> I[Pripravljalni postopek]
    I --> POR[Poravava, kadarkoli do izdaje sodbe]
    I --> |Zagotovljena kontradiktornost| J[Glavna obravnava, imamo zapisnik]
    J --> POR
    I --> |Dejansko stanje ni sporno č59| SS[sojenje na seji]
    J --> K{Upravno<BR> Sodišče<BR> odloča}
    SS --> K
    K --> |Spor zakonitosti| SZ{utemeljena}
        SZ --> |DA| SOD1["**Sodba**: ugodi in odpravi upravni akt č64"]
            SOD1 --> |lahko odloči| PND[Prepoved nadaljevanja dejan č66j in odškodninski zahtevek]
            PND -->L[Vročitev sodbe]
        SZ --> |NE| SOD3[**Sodba**:  zavrne č63]
            SOD3 --> L
    K --> |Spor polne juristikcije meritorno| SOD2["**Sodba**: upravni akt odpravi in odloči o stvari č65"]
        SOD2 --> L
    K --> |ničnost upravnega akta| S7[Sklep o ničnosti]
        S7 --> KON
    L --> M{Rok za pritožbo<BR> 15 dni}
    M -->|Pritožba vložena| N[Postopek pred Vrhovnim sodiščem]
    M -->|Ni dovoljena| PRIND[spor iz zakonitosti, ni bistvenih kršitev, ni zmotne uporabe materialnega prava li ugotovitve dejanskega stanja]
        PRIND--> PS
    M -->|Pritožba ni vložena| PS[Pravnomočnost sodbe]
    N --> OVS[Odločitev Vrhovnega sodišča pod pogojem, da je spremenjen upravni akt in meritorna odločitev ali človekove pravice]
    OVS --> PRIZ{Pritožba<BR> zavrnjena}
    PRIZ --> |DA| PS
    PRIZ --> |NE| R[Sodba razveljavljena, v primeru spora zakonitosti]
    R --> S[Vrnitve zadeve na prvo stopnjo]
    S --> J
    PS --> IZV[Izvršba sodbe]
    POR --> KON
    C4 --> KON
    IZV --> KON[Konec postopka]
    PS --> VD{dodatne<BR> možnosti}
    VD -->|Revizija vložena v 30 dneh| W[Postopek revizije]
        W --> X{Odločitev<BR> o reviziji}
        X --> |Revizija zavrnjena č85| IZV
        X --> |Revizija ugodena| S
    VD -->|obnova postopka osebe z izpitom č96| OP[Obnova postopka]
        OP --> |zavrženo| IZV
    TOZBA@{shape: doc}
    SOD1@{shape: doc}
    SOD2@{shape: doc}
    SOD3@{shape: doc}
    S7@{shape: doc}
```
