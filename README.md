# DataFlex
DataDlex elmélet és gyakorlat összefoglaló

## Elmélet
### DataFlex
- Üzleti alkalmazások készítésére alkalmas fullstack fejlesztő eszköz. 
- A legtöbb adatbázis formátummal kommunikálni képes 
- Windows és Web-es környezetben futtatható nativeszoftvert készíthetünk vele

Üzleti szoftverek célja:
Adatgyűjtés (Hibamentes, vezérelt, gyors) -> Információ (Átfogó, azonnali) -> Döntés (Jól alátámasztott)

Mi szolgálja ezt a célt?
Adatgyűjtés (Jól kialakított felületek) -> Információ (Megfelelő adatbázis struktúra) -> Döntés (Riportok, kimutatások, dashboard-ok)

Tulajdonságok:
Objektum-Orientált programozási nyelv
- Osztályok-objektumok: Objektumok egymásba ágyazva – a megjelenítést is meghatározza
- Öröklődés: Többszíntű öröklődés megengedett osztályok között
- Adatbázis motor: DataFlex, MSSQL, MySQL, Oracle, DB2, ODBC driver-ek
- Hungarian naming convention: Szabványosított fejlesztés – könnyű átláthatóság
- Data Dictionary: Adabázisok kiterjesztett tulajdonságait tartalmazza
- Makró struktúra: Fordítás nélküli módosítás

Eszközök:
- Studio: Alkalmazás készítés
- Database Explorer: Adatnézegető
- Database Builder: Adatbázis szerkesztő

Alkalmazás készítés lépései:
- Workspace létrehozás 
- Adatbázisok definiálása
- Adatelem-szótárak kidolgozása
- Egyszerű adatkezelési felületek készítése
- Összetettebb adatkezelési felületek készítése
- Batch eljárások készítése
- Csinosítás
- Riportok, lekérdezések készítése

Workspace:
Munkaterület, amely összefogja az alkalmazásunk összes elemét (.sws, .sw)

- AppHtml (Webes alkalmazás kliens fájljai)
- AppSrc (Alkalamzás forrás fájlai)
- Bitmaps (Képek könyvtára)
- DDsrc (Adatelem-szótár fájlok)
- Data (Adatbázisok, adatkapcsolatok fájlai)
- Help (Help fájlok)
- Idesrc (Studio munkafájlai)
- Programs (Futtatható progamok, ws, dll fájlok)

Fontos nyelvi szabályok:
- Sorok végén nincs semmi
- Nem case sensitive
- Típus meghatározásnál nem adunk meg értéket
- Több változót is megadhatok egy sorban
- Értékadás: move „érték” to valtozo
- Nem a matematikai precedencia szerint értékeli ki a művelteket /(1+4*2)=10 és nem 9/ -> Zárójeleket használjunk
- Logikai kifejezés kiértékelése

###Adatbázisok
Fogalmak:
- Relációs adatmodell | Logikai adatmodell, legfontosabb eleme a matematikai reláció
- Tábla | Táblában tároljuk az adatokat. Azonos sorok, különböző oszlopok
- Nézet | Állandósított lekérdezés – tábla, vagy táblák oszlopai
- Index | Gyors keresést lehetővé tevő tábla – oszlop, vagy oszlopok
- Kényszer | (Constrain) – korlátozó szabály, adathalmazt ír le
- Trigger | Eseményre adott automatikus válasz
- Kulcs | A rekordok egyediségét biztosítja – 1 elemű
- Összetett kulcs | A rekordok egyediségét biztosítja – több elemű
- Külső kulcs | Másik tábla elsődleges kulcsára hivatkozik

Loundry Share App
"A város különböző pontjain elhelyezett, önkiszolgáló rendszerben működő mosodai szolgáltató cég"
- Több telephely
- Különböző gépek (mosó, szárító, töltési súly)
- Bérlés problémája – foglalás - elszámolás
Cél:
- Kihasználtság maximalizálása
- Optimális karbantartási időszak
- Akciók 
- Cash-Flow
- Bővülés

Funkcionális függőség:
Két mező viszonya. Az „A” mező funkcionálisan függ „B ” mezőtől, ha a „B” mező értéke egyértelműen meghatározza „A” mező értékét.

Teljes funkcionális függőség:
- Egy tábla minden nem kulcs mezője függjön a kulcs mezőtől
- Minden, nem kulcs mező csak a kulcstól függjön
- Összetett kulcs esetén, minden nem kulcs mező függjön a kulcs minden elemétől

Részleges funkcionális függőség (CSAK):
- Teljes funkcionális függőség akadálya
- Összetett kulcs esetén fordulhat elő
- És nem teljesül a teljes funkcionális függőség 3. pontja: „Összetett kulcs esetén, minden nem kulcs mező függjön a kulcs minden elemétől”

Tranzitív függőség (IS):
- Minden nem kulcs mező függ a kulcstól
- Van olyan mező, ami nem csak a kulcstól függ

Normálformák – 1NF:
- Minden rekord különbözik
- A mezők száma és sorrendje azonos
- Nincsenek többértékű mezők

Normálformák – 2NF:
N:M kapcsolatok felbontása 
- A táblánk 1NF-ben legyen
- Részleges funkcionális függőségek megszüntetése – CSAK függőségek megszüntetése

Normálformák – 3NF:
- A tábla 2NF-ben legyen
- Tranzitív függőségek megszüntetése – IS függőségek megszüntetése

Adatbázis tábla létrehozás:
1. Create New Table: Studio – Table Explorer
2. Tábla sorszáma - neve: + Adabázis típusa
3. Oszlopok: Név, típus, méret, saját index
4. Index(ek)
5. Reláció(k): Adattáblák közötti kapcsolat

Data Dictionary – Adatelem-szótár:
- Adatbázis tábla tulajdonságainak kiterjesztése
- Adatok védelme
- Összefogja az üzleti szabályokat
- Minden táblához tartozhat adatelemszótár (több is)
- Osztályként kerül definiálásra

Adatbázisok --> Adatelem-szótárak --> Alkalmazás megjelenítési felülete

Tranzakciók:
Tranzakció indítása --> Adatok táblaszintű, vagy rekord szintű lokkolása --> Adatok ellenőrzése, feldolgozása és adatbázis mezők frissítése --> Van hiba?

Hiba:
Metódus megáll , tranzakció visszavonás --> Lokkolás megszűnik --> Hibaüzenet --> Err indikátor = True

Nincs hiba:
Metódus végigmegy --> Tranzakció végrehajtása --> Lokkolás megszűnik --> Err indikátor = False

Típusok:
- Insert
- Update
- Delete

INSERT - Létrehozás:
- Request_Save hatására
- File puffer megváltozott
- Nincs rekord (RowID) azonosító
- DDO fában felfelé hat

INSERT – DD események:
1. Clear_Main_File: Globális puffer ürítése – Nem relációban lévő tábla pufferének törlése
2. Creating: Csak ilyen esetben fut le – Lokkolás indul – Érték hozzáadása a lokális pufferhez
3. Update: Érték módosítása a lokális pufferben
4. Validate_Save: Megadott adatok ellenőrzése – Hiba esetén rollback + hibaüzenet
5. Attach_Main_File: Idegen kulcsok karbantartása
6. Save_Main_File: Tényleges mentés – Lokkolás vége
7. OnNewCurrentRecord: Minden tranzakció végén lefut

DELETE - Törlés:
- Request_Delete hatására
- Van rekord (RowID) azonosító
- DDO fában mindkét irányba hat
  - Szülőkben mentés
  - Gyerekben törlés
 
DELETE – DD események:
1. Relate_Main_File: Nem relációban lévő adatbázis táblákban kereshetünk
2. Validate_delete: Adatok ellenőrzése – Lokkolás indul – Hiba esetén rollback + hibaüzenet
3. Deleting: Csak Request_Delete esetén fut le – értékek hozzáadása a lokális pufferhez
4. Backout: Globális fájl pufferben a régi adatok találhatóak – adatok módosítása
5. Delete_Main_File: Tényleges törlés – Lokkolás vége
6. Clear_Main_File: Pufferek törlése - Nem relációban lévő adatbázis táblák pufferének törlése
7. OnNewCurrentRecord: Minden tranzakció végén lefut

UPDATE - Módosítás:
- Request_Save hatására
- File puffer megváltozott
- Van rekord (RowID) azonosító
- DDO fában felfelé hat

UPDATE – DD események:
1. Relate_Main_File: Nem relációban lévő adatbázis táblákban kereshetünk
2. Backout: Lokkolás indul – Globális pufferben a régi adatok – adatok módosítása
3. Update: Lokális pufferben az új adatok – adatok módosítása
4. Validate_Save: Megadott adatok ellenőrzése – Hiba esetén rollback + hibaüzenet
5. Save_Main_File: Tényleges mentés – Lokkolás vége
6. OnNewCurrentRecord: Minden tranzakció végén lefut

DATAFLEX adatbázis tulajdonságok:
- 15 index: Maximum 15db index definiálható + sorszám hivatkozás
- Adatbázis: Nincs központi fájl, minden adattáblához külön fájlok
- Recnum: Rekord azonostó (1NF) nem változtatható futó sorszám
- Index szegmens: Maximum 16 szegmens – 255 byte
- Lokkolás: Fájl szintű lokkolás
- Main index: Elsődlegesen használt index

DataDictionary - Reláció:
- Összekötöttség – gyerek keresés magával rántja a szülőt is (1:N)
- Csatlakozások – mentés és keresés előtt a kapcsolt mezők tartalma mindig azonos
- Kényszerítés – csak az adott adatbázis szelet látható
- Jóváhagyás és mentés – gyerek mentés esetén az összes szülő vizsgálata és mentése

### Információ
Riportálás, listák készítése

CÉL: adatból információ legyen

Hol, mire használjuk:
- Visszakeresés: Könyvelés, egyeztetés
- Címke: Vonalkód, QR kód
- Azonosítás: Árut kísérő dokumentum
- Dashboard, KPI: Vezetői információs pult
- Ellenőrzés: Leletár

Technológia - ETL:
1. Extract: Adatok elérése, kivonatolás
2. Transform: Transzformáció, átalakítás
3. Load: Betöltés

4Q – modell, Transzformáció:
- Csoportosítás: Csoportosítandó adatok megadása
- Összegzés: Csoportosításban szereplő összegek
- Részletek: Riportban megjelenő alap adatok
- Szűrés: Adatbázis szelet

Listázási lehetősége:
- WinPrint: Beépített Windows nyomtatási motorra épül
- DataFlex Reports: Vizuális riport szerksztő eszköz
- Dynamic AI: Üzleti intelligencia(BI) eszköz

WinReport:
- Formázható nyomtató motor, Windows használat
- BasicReport alosztálya
- Szöveges lista készítés
- Karakterek formázása
- Eredmény: képernyőn megjelenő lista
- DD-n keresztüli kapcsolat
- Nem lehet fájlba nyomtatni!

DataFlex Reports:
- Vizuális, külső szerkesztő felület
- Közvetlen csatlakozás DB-hez
- Egymásba ágyazható listák
- Vonalkód, QR kód generálás
- Nyomtatás Pdf,Excel,stb. formátumban
- Külső könyvtár kapcsolat DF-be

Dynamic AI:
- BI (Business Intelligence) eszköz
- Webes felületű szekesztő
- Közvetlen csatlakozás DB-hez
- Egymásba ágyazható listák
- Nyomtatás Pdf,Excel,stb. formátumban
- Monitorozás, automatizálás

WinPrint lista szekciók:

| Kód | leírás | hosszabb leírás |
| --- | --- | ---|
| Page_Top | Minden listában | Minden oldal tetején megjelenik |
| Report_Header | Minden listában | Lista elején 1x jelenik csak meg |
| Page_Title | Minden listában | Minden oldalon a Page_Top után jelenik meg |
| SubHeader_Ini1…N | Csoportosítás esetén | A csoportosított elemek első előfordulásakor, minden listában csak 1x (töréspont) |
| Sub_Header1…N | Csoportosítás esetén | A csoportosított elemek első előfordulásakor (töréspont) |
| Body | Minden listában | Elemek részletes listája, minden rekord esetén |
| Sub_Total1…N | Csoportosítás esetén | A csoportosított elemek utolsó előfordulásakor, összeg képzés |
| Total | Csoportosítás esetén | A lista utolsó eleme után, végösszesen képzés, utolsó Sub_Total után |
| Page_Total | Csoportosítás esetén | Oldaldobás előtt, összegzés |
| Page_Footer | Minden listában | Minden oldal alján, az utolsó oldalon a Page_Total után |
| Report_Footer | Minden listában | Listánként csak 1x, az utolsó odalon Page_Total után |
| Page_Bottom | Minden listában | Minden oldalon a záró elem |



## Gyakorlat
Változók definiálása:
- String sName sCity sZipCode | Karaktereket tartalmazó változók
- Number nErtek | Lebegőpontos számok
- Integer iCount iAmount | Egész számok
- RowId riCustomer | Hexadecimális formában, adatbázis rekord azonosítók
- Variant vWordDocuments vWordDocument | Dinamikusan változó típusú értékek,
- String[] sNames sCities | 1 dimenziós karaktereket tartalmazó vektor
- String[5] sCustomers | 5 karakteres elemet tartalmazó vektor
- Integer[][] iOrders | 2 dimenziós egész számokat tartalmazó tömb

Struktúra:
Struct tCustomer
  integer iNumber
  string sName
  string sCity
End_struct

tCustomer Customer1 Customer2
Move 1 to Customer1.iNumber
Move Customer1 to Customer2

Érték adás:
- Move 1 to iCount
- Move (1+1) to iCount
- Move (iCount+1) to iCount
- Move (iCount*iCount) to iCount
- Move iCount to iCount2

Tulajdonság értékének elérése:
- Get pbReportErrors to bReportErrors

Tulajdonság értékének beállítása:
- Set pbReportErrors to bReportErrors

Ciklus:
- For … loop
- Repeat … Until
- While … loop

For i from 0 to 10
  showln 1
Loop

Értéklista:
Enum_List
  define c_statusWrong
  define c_statusOk
  define c_statusTalan
end_enum_list

Vezérlések
Feltétel if
- Pl. if (iCount=10) move 0 to iCount
- Pl. if (iCount=10) move 0 to iCount
  Else move (iCount+1) to iCount
- Pl. if (iCount>0) if (iCount<10) move (iCount+1) to icount
  if (iCount>0 and iCount<10) move (iCount+1) to icount
Feltétel case
case Begin
  case (feltétel)
  //műveletek
  case break
  case (feltétel)
  //műveletek
  case break
case End

Kód:
```
Integer iSpacePos
String sLine sWord
Repeat
  Move (Pos(' ',sLine) to iSpacePos
  If (iSpacepos>0) Begin
    Move (Left(sLine,iSpacePos)) to sWord
    Move (Right(sLine,Length(sLine)-iSpacePos)) to sline
  End
  Else Begin
    Move sLine to sWord
    Move '' to sLine
  End
Until (sLine="")
String sLine
Direct_Input "c:sometext.txt"
While (not SeqEof)
  Readln sLine
Loop
Close_Input
```

Eljárás:
```
Procedure Name {Global | Desktop} {Returns Type}
End_procedure

Procedure name {global|desktop} type param1 type param2 … type paramN {returns type}
End_procedure

Byval & byRef
Procedure Name global string byref sSzoveg
End_procedure
```
```
Procedure ShowToday
  date dToday
  sysdate dToday
  showln dToday
End_procedure
Send showtoday
```

Függvény:
```
Function Name {Global | Desktop} Returns Type
  function_return value
End_function
```

### Órai feladatok:
Eljárások:
```
Use DfAllEnt.pkg

Function MultiplyByFive Integer iVal Returns Integer
    Function_Return (iVal*5)
End_Function

Procedure UpperDesc String ByRef sDesc
    Move (Uppercase(sDesc)) to sDesc
End_Procedure

Procedure Feladat Integer iNum String sDesc
    Get MultiplyByFive iNum to iNum
    Move (MultiplyByFive(Self,iNum)) to iNum
    Send UpperDesc (&sDesc)
    Send Info_Box (SFormat("Feladat: %1, %2",iNum,sDesc)) "Hello"
End_Procedure

Send Feladat 4 "Valami"
Send Feladat 12 "Valami más"
```

Változók:
```
Use DfAllEnt.pkg //fontos!!!

Procedure Valtozok
    String sText
    
    Move "Hello változók" to sText
    
    Send Info_Box sText "Üzenet"
End_Procedure

Send Valtozok
```

Tömbök:
```
Use DfAllEnt.pkg

Procedure DemoArray
    String[] aNames
    Integer iIndex
    
    Move "John" to aNames[0]
    Move "Stephen" to aNames[1]
    Move "Nick" to aNames[2]
    Move "Harm" to aNames[3]
    
    Move (SortArray(aNames)) to aNames
    
    For iIndex from 0 to (SizeOfArray(aNames)-1)
        Showln aNames[iIndex]
    Loop
    Move (SearchArray("Nick",aNames)) to iIndex
    Showln (String(iIndex)+".elem a tömbben.")
    
End_Procedure

Procedure MultiDimArray
    String[][] aaGrid
    String sResult
    Integer iX iY
    
    For iX from 0 to 4
        For iY from 0 to 4
            Move (Character(ix+65)+"."+String(iY)) to aaGrid[iX][iY]
        Loop
    Loop
    
    For iX from 0 to (SizeOfArray(aaGrid)-1)
        Move "" to sResult
        For iY from 0 to (SizeOfArray(aaGrid[iX])-1)
            Move (sResult+" "+aaGrid[iX][iY]) to sResult
        Loop
        Showln sResult
    Loop
    
End_Procedure

//Send DemoArray
Send MultiDimArray
Send Info_Box "Kész" 
```

Struct (Rekord):
```
Use DfAllEnt.pkg
Use cJsonObject.pkg

Struct stOrder
    Integer iId
    Date dDate
    Number nTotal
End_Struct

Struct stCustomer
    Integer iId
    String sName
    String sCity
    stOrder[] aOrders
End_Struct

Procedure DisplayCust stCustomer tCust
    String sResult
    Handle hoJson
    
    Get Create (RefClass(cJsonObject)) to hoJson
    Send DataTypeToJson of hoJson tCust
    Set peWhiteSpace of hoJson to jpWhitespace_Pretty
    Get Stringify of hoJson to sResult
    Send Destroy of hoJson
    Send Info_Box sResult
End_Procedure

Procedure DemoStruct
    stCustomer tCust
    
    Move 12 to tCust.iId
    Move "DataAcces" to tCust.sName
    Move "Miami" to tCust.sCity
    
    Move 3 to tCust.aOrders[0].iId
    Move (DateSet(2024,09,17)) to tCust.aOrders[0].dDate
    Move 123.99 to tCust.aOrders[0].nTotal
    
    Move 1 to tCust.aOrders[1].iId
    Move (DateSet(2024,09,18)) to tCust.aOrders[1].dDate
    Move 1236.99 to tCust.aOrders[1].nTotal
    
    Move 2 to tCust.aOrders[2].iId
    Move (DateSet(2024,09,19)) to tCust.aOrders[2].dDate
    Move 1237.99 to tCust.aOrders[2].nTotal
    
    move (SortArray(tCust.aOrders)) to tCust.aOrders
    Send DisplayCust tCust
End_Procedure

Send DemoStruct
```

Osztályok:
```
Use DfAllEnt.pkg

Class cPerson is a cObject
    Procedure Construct_Object
        Forward Send Construct_Object
        
        Property String psFirstname ""
        Property String psLastname ""
    End_Procedure
    
    Function HelloMessage Returns String
        String sFirst sLast
        
        Get psFirstname to sFirst
        Get psLastname to sLast
        
        Function_Return (sFirst+" "+sLast+" says hi!")
    End_Function
    
    Procedure SayHello
        String sMsg
        Get HelloMessage to sMsg
        Showln sMsg
    End_Procedure
End_Class

Class cEmpl is a cPerson
    Procedure Construct_object
        Forward Send Construct_Object
        
        Property String psFunction ""
    End_Procedure
    
    Function HelloMessage Returns String
        String sFunction sMsg
        Forward Get HelloMessage to sMsg
        
        Get psFunction to sFunction
        
        Function_Return (sFunction+", "+sMsg)
    End_Function
End_Class

Object oJohn is a cPerson
    Set psFirstname to "John"
    Set psLastname to "Tuohy"
End_Object

Object oHarm is a cEmpl
    Set psFirstname to "Harm"
    Set psLastname to "Wibier"
    Set psFunction to "CTO"
End_Object

Procedure DynamicObject
    Handle hoStephen
    
    Get Create (RefClass(cEmpl)) to hoStephen
    
    Set psFirstname of hoStephen to "Stephen"
    Set psLastname of hoStephen to "Meeley"
    Set psFunction of hoStephen to "COO"
    
    Send SayHello of hoStephen
    
    Send Destroy of hoStephen
End_Procedure

Send SayHello of oJohn
Send SayHello of oHarm

Send DynamicObject

Send Info_Box "Kész"
```

Adatbázisban alap dolgok lefutásának beállítása:
```
    //INSERT
    //UPDATE
    Procedure Update
        Forward Send Update
        Move (lap.osszdij+(laptetel.menny*laptetel.ar)) to lap.osszdij
    End_Procedure
    
    //UPDATE
    //DELETE
    Procedure Backout
        Forward Send Backout
        Move (lap.osszdij-(laptetel.menny*laptetel.ar)) to lap.osszdij
    End_Procedure

    Function Validate_Save Returns Integer
        Integer iRetVal
        Forward Get Validate_Save to iRetVal
        
        If (not(iRetVal)) Begin
            If (laptetel.menny<=0) Begin
                Error 501 "Mennyiség nem lehet 0, vagy negatív szám!"
                Move 501 to iRetVal
            End
            If (laptetel.ar<0) Begin
                Error 502 "Negatív ár nem rögzíthető!"
                Move 502 to iRetVal
            End
        End
        
        
        
        Function_Return iRetVal
    End_Function

    Procedure Creating
        Forward Send Creating
        Move (CurrentDateTime()) to laptetel.crdate
        Move (Idobelyeg(Self)) to laptetel.crido
    End_Procedure

    Procedure Save_Main_File
        Boolean bChanged
        Integer iFile
        
        Get Main_File to iFile
        Get_Attribute DF_FILE_CHANGED of iFile to bChanged
        If (bChanged) Begin
            Move (CurrentDateTime()) to laptetel.lmdate
            Move (Idobelyeg(Self)) to laptetel.lmido
        End
        
        Forward Send Save_Main_File
    End_Procedure
```

## zh
### Workspace létrehpzása
Dataflex-ben workspace létrehozás

### Projekt létrehozása
Új projektet a legördülő File (Fájl) menüben, a New (Új), majd a Windows Project (Projekt) pont alatt hozhatunk létre.

### Táblázat létrehozása
Legördülő View (Nézet) menü Table Explorer (Táblázatböngésző) opciójával, vagy a nézet-eszköztáron elhelyezett gombbal aktiválhatja azt. A lista fölött látható gomb táblázatok készítésére, leejtésére, illetve módosításhoz való megnyitására használható. Ugyanez a funkció az úszó menüben is megtalálható, amelyet jobb egérkattintással nyithat meg a Table Explorer ablakban. Kattintson tehát a Create New Table (Új táblázat létrehozása) gombra (az első gomb), vagy válassza ki a Create New Table lehetőséget az úszó menüből. Ki kell választani a Dataflex Database-t (embedded) és azon belül meg kell adni az adatbázis nevét. Ez után már lehet felvenni oszlopokat, az után indexes megjelenítést majd relationships-et (ha meg lehet már tenni)

#### Data Dictionaries beállítása
Itt lehet megkötéseket írni az adatbázis oszlopaival kapcsolatban, illetve eventeket létrehozni (létrehozáskor mi történjen stb).
Fontos beállítások:
- Capslock
- Required
- Protect Value
- Auto Increment (indexhez)
- Default Value

Ezenkívül itt lehet még Validation Objects beállítani a megfelelő fülön

### Adatbeviteli nézet
File-ra, azon belül a New-ra, majd a View / Report (Nézet / Jelentés) opcióra, Data Entry View Wizard

#### Sorrend megváltoztatása
Code Explorer - kijelölés és a felső gombok

### Autamatikus kulcs
Plusz táblázat, ahol a növekedő kulcsok vannak. Ahhoz, hogy ebből valóban rendszerfájl legyen, a táblázat DF_FILE_IS_SYSTEM_FILE tulajdonságát állítsa True-ra. 

### Kiválasztási lista
New (Új), Dialog / Lookup (Párbeszéd / Keresés) opciót, és elindítjuk a Lookup Wizard-ot (Keresés varázslót)

### Mutassa az összes elemet szűrve
-	Hozzon létre egy új üres nézetet (válassza ki a Data Entry View (Adatbeviteli nézet) sablont).
-	Használja a DDO Explorer-t a Media és a People kiválasztásához.
-	Húzza a FirstName-et és a LastName-et a nézetre.
-	Használja az Object Properties-t a FirstName és a LastName címkék megváltoztatásához.
-	Igazítsa az objektumokat vízszintesen.
-	Távolítsa el az azonnal gombot a LastName oszlopból (keresse meg a Prompt_Button_Mode-ot az Object Properties listából, és állítsa PBPromptOff -ra). Ezzel nem távolítja el egészen a keresési listát (még mindig megnyomhatja az F4 gombot, vagy kiválaszthatja a keresést az eszköztárról vagy az úszó menüből), a vizuális útmutatást viszont igen. A keresési lista eltávolításához egy kódsort kellene hozzáadnia a People adatszótár-objektumához. 
-	Ellenőrizze a DDO Explorer-ben, hogy a szűkítés a People-ra van-e beállítva (lásd a képen). Ha nem így van, a DDO Explorerben az egér jobb gombjával kattintson a Media-táblázatra, és válassza ki az Add/Change (Hozzáadás/Változtatás) szűkítést. Adjon hozzá szűkítést a People-höz (ellenőrizze a Main (Fő) DD-t is), a szerkezete pedig olyan legyen, mint ahogy a jobboldali képen látható.
-	A fogd-és-vidd segítségével hozzon létre egy cDbCJGrid osztályú objektumot az osztálypalettáról.
-	A DDO Column Selector-ból (DDO Oszlopválasztóból) húzza a Title, Author és Type oszlopokat a Media-ból a rácsra

### Képek
-	Nyissa meg az Media táblázatot, ha még nincsen megnyitva, és adjon hozzá egy Picture (Kép) elnevezésű oszlopot. 
-	A típusa ASCII, a hossza 255 legyen. Maga a kép nem itt kerül tárolásra, azonban minden bejegyzés tartalmazni fog egy, a kép helyére (mappa) és nevére mutató hivatkozást.
-	Nyissa meg ismét a Media nézetet a Studio-ban, és nagyítsa fel kissé. 
-	Az osztálypalettában az adatvezérlők között keresse ki a dbBitmap-et, és húzza át a Media nézetre.
-	Rendelje hozzá a Data Source-ot (Adatforrást) (Beviteli tételt) a Media.Picture oszlophoz a Properties (Tulajdonságok) panelen a Binding (Összekötés) lapfül alatt.
-	Fordítsa át és indítsa el az alkalmazást (F5).

### Jelentések
New (Új), View / Report, Winprint2 report wizard
