# Cvičenie 6: Aktualizácia, zabezpečenie OS Windows a systémové politiky

## Úloha 1: Windows Update

### 1.1 Pojmy

1. Čo je Windows Update a na čo slúži?
-> program na vyhľadávanie aktualizácií
2. Čo znamená označenie KB (napr. KB5034441)?
-> bezpečnostné záplaty, oprava chýb
3. Vysvetlite rozdiel medzi aktualizáciou kvality (Quality) a aktualizáciou funkcií (Feature):
-> aktualizácia kvality (Quality) zabezpečuje bezpečnostné záplaty, opravy chýb a aktualizácia funkcií (Feature) zabezpečuje nové funkcie, veľké zmeny
4. Prečo je nebezpečné neaktualizovať systém? Uveďte reálny príklad:
-> diery v systéme sa nezaplátajú, je nekompatibilný, chyby v systéme sa neopravia, realnym príkladom bol WannaCry ktorý nakazil iba počitače ktoré neboli aktualizované
### 1.2 Praktická časť

**Otvorte** Nastavenia → Windows Update:

| Otázka | Odpoveď |
|--------|---------|
| Je systém aktuálny? (Áno/Nie) | Nie |
| Koľko aktualizácií čaká na inštaláciu? | 11 |
| Dátum poslednej nainštalovanej aktualizácie | 1.3.2026 |
| KB číslo poslednej aktualizácie | KB5063261 |

**Spustite v CMD:** `wmic qfe list brief /format:table`

| Otázka | Odpoveď |
|--------|---------|
| Koľko aktualizácií vidíte vo výpise? | 32 |
| HotFixID poslednej aktualizácie | KB5063979 |

**Otvorte** `services.msc` a nájdite službu Windows Update:

| Otázka | Odpoveď |
|--------|---------|
| Stav služby (Spustená/Zastavená) | spustené |
| Typ spustenia (Automaticky/Ručne/Zakázané) | ručné |

5. Čo by sa stalo, keby ste typ spustenia služby Windows Update zmenili na "Zakázané"?
-> nechodili by aktualizácie
---

## Úloha 2: Zabezpečenie Windows

### 2.1 Pojmy

1. Čo je Windows Defender?
-> antivírus
2. Aký je rozdiel medzi rýchlym a úplným skenovaním?
-> rýchle skontroluje najčastejšie miesta (pamäť, spustenie, temp) a úplne skontroluje celý disk
3. Čo je firewall a na čo slúži? Vysvetlite vlastnými slovami:
-> filtruje prichádzajúce pakety
4. Windows firewall má 3 profily – vymenujte ich a napíšte, kedy sa ktorý aktivuje:

   - **Doménový:** -> firemná sieť
   - **Súkromný:** -> domáca sieť
   - **Verejný:** -> kaviareň, letisko, hotel

5. Čo znamená príkaz `wf.msc` a čo `firewall.cpl`? Aký je medzi nimi rozdiel?
-> 
### 2.2 Praktická časť

**Otvorte** Zabezpečenie systému Windows a zapíšte stav:

| Komponent | Stav (OK / Varovanie / Chyba) |
|-----------|-------------------------------|
| Ochrana pred vírusmi a hrozbami | OK |
| Firewall a ochrana siete | OK |

**Spustite v CMD:** `netsh advfirewall show allprofiles state`

| Profil | Stav (ON/OFF) |
|--------|---------------|
| Doménový | ON |
| Súkromný | ON |
| Verejný | ON |

6. Prečo by ste nemali firewall vypínať, aj keď vám niečo nefunguje? Čo by ste mali urobiť namiesto toho?
-> lebo prestane filtrovať sieťovú komunikáciu a môžu nám prísť škodlivé pakety ktoré by zapnutý firewall odfiltroval
---

## Úloha 3: Lokálne politiky – gpedit.msc

### 3.1 Pojmy

1. Čo je gpedit.msc a na čo slúži?
-> nástroj na centrálnu správu nastavení Windows na jednom PC
2. Aký je rozdiel medzi lokálnou politikou a doménovou politikou?
-> lokálna je na jednom pc a doménová na celej sieti
3. Čo robí príkaz `gpupdate /force`? Kedy ho musíte spustiť?
-> aplikovanie politík
4. Čo robí príkaz `gpresult /r`?
-> výpis aplikovaných politík
5. Vysvetlite, čo je politika uzamknutia účtu a proti akému typu útoku chráni:
-> po niekoľkých pokusoch o zadanie hesla uzamkne účet na nejakú dobu. chráni pred brute-force útokom
### 3.2 Praktická časť – politiky hesiel

**Otvorte** `gpedit.msc` → Konfigurácia počítača → Nastavenia systému Windows → Nastavenia zabezpečenia → Politiky účtov → Politika hesiel

Zapíšte aktuálne hodnoty:

| Politika | Aktuálna hodnota |
|----------|-------------------|
| Minimálna dĺžka hesla | 0 znakov |
| Maximálny vek hesla | 42 days |
| Heslo musí spĺňať požiadavky na zložitosť | nie |
| Vynútiť históriu hesiel | áno |

6. Prečo je dôležité vynútiť históriu hesiel? Čo by sa stalo bez nej?
-> aby sa zabranilo opakovaniu hesiel. použivali by sa tie isté heslá
### 3.3 Praktická časť – uzamknutie účtu a CMD

**Nastavte politiku uzamknutia účtu:**

1. Prah uzamknutia → **5 pokusov**
2. Potvrďte dobu uzamknutia **30 minút**
3. Spustite `gpupdate /force`

- [ ] Hotovo

**Vyskúšajte zakázať CMD:**

Cesta: Konfigurácia používateľa → Šablóny pre správu → Systém → Zabrániť prístupu k príkazovému riadku

1. Zapnite politiku → spustite `gpupdate /force` → skúste otvoriť CMD

| Otázka | Odpoveď |
|--------|---------|
| Čo sa stalo po pokuse otvoriť CMD? | otvoril sa mi cmd ale keď som stlačil nejakú klávesu tak sa vypol |
| Funguje PowerShell naďalej? (Áno/Nie) | áno |

2. **DÔLEŽITÉ:** Vráťte politiku späť na **Nekonfigurované** a spustite `gpupdate /force`!

- [ ] Vrátené
