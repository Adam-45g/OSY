# Cvičenie: Príkazový riadok OS — `ls`, `cd`, `cp`, `rm`, `mv`

> Vyplň odpovede pod každú otázku. Pri otázkach typu áno/nie zaškrtni `- [x]`. Výstupy z terminálu prilep do code blokov.

---

## Úloha 1 — Orientácia v systéme

> Otvor terminál (`Ctrl + Alt + T`). Všetky nasledujúce príkazy píš v **tvojom domove**.

### 1.1 Napíš `pwd` a zapíš výstup (absolútna cesta k tvojmu domovu):

```
/home/student
```

### 1.2 Napíš `ls`. Vymenuj aspoň **3 položky**, ktoré vidíš:

- Desktop
- Documents
- Downloads

### 1.3 Napíš `ls -l`. Nájdi:

- **Jeden priečinok** (začína `d`): drwxr
- **Jeden súbor** (začína `-`): -xr-x

### 1.4 Napíš `ls -a`. Zapíš aspoň **3 skryté položky** (začínajú `.`):

- cache
- config
- dmrc

---

## Úloha 2 — Navigácia po strome

> Po každom kroku napíš **čo ti ukázal `pwd`**.

### 2.1 Spusti `cd ~`, potom `pwd`:

```
/home/student
```

### 2.2 Spusti `cd ..`, potom `pwd`:

```
/home
```

> **Pozor:** správna odpoveď je `/home` (nie `/home/<tvoje_meno>`). Ak máš niečo iné, nerozumel si `..`.

### 2.3 Spusti `cd /`, potom `pwd`:

```
/
```

### 2.4 Spusti `cd -`. Čo ti vypíše shell na obrazovku?

```
/home
```

### 2.5 Ako sa najrýchlejšie vrátiš do svojho domovského adresára? Napíš **dva spôsoby**:

1. cd -
2. pwd

---

## Úloha 3 — Kopírovanie

> Postupne vykonaj nasledujúce príkazy. Po každom skontroluj výsledok cez `ls`.

### 3.1 Vytvor štruktúru:

```bash
cd ~
mkdir skola
touch poznamky.txt
touch uloha.txt
```

Napíš výstup `ls` po týchto príkazoch:

```
Desktop    Downloads  Pictures      Public  Templates  Videos
Documents  Music      poznamky.txt  skola   uloha.txt
```

### 3.2 Skopíruj súbor do priečinka:

```bash
cp poznamky.txt skola/
```

Napíš výstup `ls skola/`:

```
poznamky.txt
```

### 3.3 Duplikuj súbor pod novým menom:

```bash
cp poznamky.txt zaloha.txt
```

Existuje teraz aj **originál** `poznamky.txt`, aj **kópia** `zaloha.txt`?

- [x] áno
- [ ] nie

### 3.4 Skús skopírovať priečinok **BEZ** `-r`:

```bash
cp skola zaloha_skola
```

**Presná chybová hláška:**

```
cp: -r not specified; omitting directory 'skola'
```

### 3.5 Teraz s `-r`:

```bash
cp -r skola zaloha_skola
```

Napíš výstup `ls`:

```
Desktop    Downloads  Pictures      Public  Templates  Videos        zaloha.txt
Documents  Music      poznamky.txt  skola   uloha.txt  zaloha_skola
```

### 3.6 Prečo `cp` potrebuje `-r` pri priečinkoch?
Lebo potom nevie pre aky priecinok
---

## Úloha 4 — Premenovanie a presun

### 4.1 Premenuj súbor:

```bash
touch test.txt
mv test.txt hotovo.txt
```

Vidíš ešte `test.txt` v `ls`?

- [ ] áno — ostal
- [x] nie — zmizol (premenovaný)

### 4.2 Presuň do priečinka:

```bash
mv hotovo.txt Documents/
```

Napíš výstupy:

```
$ ls
Desktop    Downloads  Pictures      Public  Templates  Videos        zaloha.txt
Documents  Music      poznamky.txt  skola   uloha.txt  zaloha_skola

$ ls Documents/
hotovo.txt
```

### 4.3 Presuň celý priečinok (**bez** `-r`!):

```bash
mv skola zaloha_skola2
```

Dostal si chybovú hlášku?

- [ ] áno
- [x] nie

### 4.4 Doplň pravidlo:

**`mv` súbor priečinok/** → (presun)
**`mv` súbor novy_nazov** → (premenovanie)

> *Ako `mv` rozozná, ktorú akciu má urobiť?*
podla lomitka
---

## Úloha 5 — Mazanie ⚠️

> **Pozor:** v Linuxe **neexistuje Kôš**. Čo zmažeš, je preč.
> **Nepúšťaj** `rm -rf` na nič mimo vlastného testovacieho priečinka.

### 5.1 Zmaž súbor:

```bash
touch zmaz.txt
rm zmaz.txt
```

Existuje ešte `zmaz.txt` v `ls`?

- [ ] áno
- [x] nie

### 5.2 Skús zmazať priečinok **BEZ** `-r`:

```bash
rm zaloha_skola
```

**Presná chybová hláška:**

```
rm: cannot remove 'zaloha_skola': Is a directory
```

### 5.3 Teraz s `-r`:

```bash
rm -r zaloha_skola
```

Napíš výstup `ls` po zmazaní:

```
Desktop    Downloads  Pictures      Public     uloha.txt  zaloha_skola2
Documents  Music      poznamky.txt  Templates  Videos     zaloha.txt
```

### 5.4 Kde skončí vymazaný súbor v Linuxe?

> *(Pozor, otázka s pascou. Pomysli, predtým než odpovieš.)*
nikde, ked ho zmazate tak je to definitivne

### 5.5 Napíš **vlastnými slovami**, prečo je príkaz `rm -rf /` **extrémne nebezpečný**:
lebo ked nieco zmazem tak uz to neviem obnovit
---

## Bonus — tab completion a history

### B.1 Skús napísať `cd Doc` a stlačiť **Tab**. Čo sa stalo?

### B.2 Stlač **šípku hore** v termináli. Čo sa stalo?

### B.3 Napíš **tvoj obľúbený objav** z dnešnej hodiny (príkaz, skratka, trik):

---

## Záver

Ktorý príkaz ti prišiel najužitočnejší a prečo?
