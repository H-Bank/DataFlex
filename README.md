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



