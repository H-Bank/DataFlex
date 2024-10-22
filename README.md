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
