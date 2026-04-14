# Analýza možností používania Linuxu na Windows PC (bez preinštalovania)

## Východiskové parametre

- CPU: AMD A8-5600K APU with Radeon HD Graphics @ 3.60 GHz  
- RAM: 8 GB (6,93 GB použiteľnej pamäte)  
- Systém: Windows 10 Pro 64-bit
- Disk: HDD 233 GB + HDD 466 GB  
- Internet: maximálne 5 Mbps  

---
# 1. Dual boot

## Výhody
- plné využitie hardvéru bez vrstvy Windows
- najvyšší možný výkon Linuxu na tomto zariadení
- stabilné a natívne prostredie
- vhodné na dlhodobé používanie

## Nevýhody
- nutnosť rozdelenia diskov
- riziko chýb pri inštalácii bootloadera
- nutnosť reštartu pri prepínaní systémov

## Vhodnosť
Veľmi vysoká. Ide o najlepší spôsob použitia Linuxu na tomto počítači z hľadiska výkonu.

---

# 2. WSL

## Výhody
- jednoduchá inštalácia a používanie
- bez zásahov do diskov
- vhodné na vývoj a terminálové nástroje
- rýchly prístup k Linux príkazom

## Nevýhody
- Windows stále spotrebúva zdroje
- slabšia podpora grafického prostredia
- HDD obmedzuje výkon súborového systému
- nejde o plnohodnotný Linux desktop

## Vhodnosť
Vysoká. Ide o najlepší kompromis medzi jednoduchosťou a funkčnosťou.

---

# 3. Docker (cez WSL2)

## Výhody
- vhodné na vývoj a testovanie aplikácií
- rýchle spúšťanie služieb
- izolované prostredie
- menšia záťaž než plná virtualizácia

## Nevýhody
- závislosť od WSL2
- viac vrstiev systému
- HDD výrazne znižuje výkon pri práci s dátami
- nejde o plnohodnotný operačný systém

## Vhodnosť
Stredná. Vhodné hlavne pre vývojárske účely.

---

# 4. Live USB Linux

## Výhody
- žiadne zmeny v systéme
- plné grafické prostredie
- vhodné na testovanie distribúcií

## Nevýhody
- pomalý štart a reakcie systému
- obmedzenia USB a HDD
- bez uloženia dát (ak nie je nastavená persistence)
- nižší výkon

## Vhodnosť
Stredná až nízka. Vhodné na testovanie, nie na bežnú prácu.

---

# 5. VirtualBox

## Výhody
- jednoduché nastavenie
- izolované prostredie
- bezpečné testovanie

## Nevýhody
- vysoká záťaž CPU
- delenie RAM medzi systémy
- HDD výrazne spomaľuje výkon
- slabý výkon grafického prostredia

## Vhodnosť
Nízka. Nevhodné pre dlhodobé používanie na tomto hardvérii.

---

# 6. Linux v prehliadači

## Výhody
- bez inštalácie
- okamžitý prístup
- funguje na akomkoľvek zariadení

## Nevýhody
- veľmi slabý výkon
- závislosť od internetového pripojenia
- obmedzené funkcie
- vhodné len na demonštráciu

## Vhodnosť
Veľmi nízka. Nepoužiteľné na reálnu prácu.

---

# Porovnanie riešení

| Riešenie | Výkon | Pohodlie | Použiteľnosť | Vhodnosť |
|----------|-------|----------|--------------|----------|
| Dual boot | vysoký | nízke | vysoká | najlepšia |
| WSL | vysoký | veľmi vysoké | vysoká | veľmi dobrá |
| Docker | stredný | vysoké | stredná | špecializovaná |
| Live USB | stredný | vysoké | nízka až stredná | testovanie |
| VirtualBox | nízky | stredné | nízka | nevhodné |
| Browser Linux | veľmi nízky | vysoké | veľmi nízka | nepoužiteľné |

---

# Závery

- Najlepší výkon: dual boot  
- Najlepší kompromis: WSL  
- Vývojárske rozšírenie: WSL + Docker  
- Testovanie: Live USB  
- Neodporúčané: VirtualBox a browser-based Linux
