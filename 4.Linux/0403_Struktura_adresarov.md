# Cvičenie: Štruktúra adresárov v Linuxe + POSIX

> Vyplň odpovede pod každú otázku. Pri otázkach typu áno/nie zaškrtni `- [x]`. Výstupy z terminálu prilep do code blokov.
> **Dnes nič nemažeme ani nemeníme** — iba pozeráme.

---

## Úloha 1 — Programy v systéme

### 1.1 Spusti `ls /bin | head` a vymenuj **5 príkazov**, ktoré poznáš:

- 7z
- 7za
- 7zr
- aa-enabled
- aa-exec

### 1.2 Spusti `which ls`. Kde reálne leží `ls`?

```
/usr/bin/ls
```

### 1.3 Spusti `which` s nejakým iným programom (napr. `python3`, `nano`, `firefox`):

```bash
which python3
```

**Výstup:**

```
/usr/bin/python3
```

### 1.4 Aký je rozdiel medzi `/bin` a `/sbin`?

> *(Stačí jedna veta.)*
/bin je pre kazdeho uzivatela a sbin len pre spravcu
---

## Úloha 2 — Konfigurácie a používatelia

### 2.1 Spusti `cat /etc/hostname`. Ako sa volá tvoj počítač?

```

```

### 2.2 Spusti `cat /etc/passwd | grep $USER`. Skopíruj **celý riadok**:

```
student:x:1000:1000:student,,,:/home/student:/bin/bash
```

### 2.3 Z tohto riadku zisti:

- **UID** (tretie pole, oddelené `:`): 1000
- **Shell** (posledné pole): bash
- **Domov** (predposledné pole): bin

### 2.4 Aké **používateľské meno** má UID 0?

> *(Tip: pozri prvý riadok `/etc/passwd`.)*
student
---

## Úloha 3 — Prieskum systému

> Pre tieto úlohy nepotrebuješ `sudo` — všetko je verejne čitateľné.

### 3.1 Aký máš procesor? Spusti:

```bash
cat /proc/cpuinfo | grep "model name" | head -1
```

```
model name	: Intel(R) Core(TM) i5-5300U CPU @ 2.30GHz
```

### 3.2 Koľko máš RAM? Spusti:

```bash
cat /proc/meminfo | head -3
```

```
MemTotal:        2015588 kB
MemFree:          202816 kB
MemAvailable:     960536 kB
```

### 3.3 Ako dlho beží systém? Spusti `uptime`:

```
 04:37:41 up 30 min,  1 user,  load average: 1.27, 1.27, 1.40
```

### 3.4 Vymenuj **3 logy**, ktoré nájdeš v `/var/log/`:

```bash
ls /var/log/ | head
```
- alternatives.log
- apt
- auth.log

### 3.5 Aké disky / partície máš? Spusti:

```bash
ls /dev | grep sd
```

```
sda
sda1
sda2
sda3
```

### 3.6 Bonus — spusti `uname -a` a zapíš výstup:

```

```

---

## Úloha 4 — POSIX v praxi

### 4.1 Funguje `ls -la` aj na **macOS**?

- [x] áno
- [ ] nie

### 4.2 Funguje `ls -la` v **CMD na Windowse** (bez WSL)?

- [ ] áno
- [x] nie

### 4.3 Prečo rovnaký bash skript beží na **Linuxe aj na MacBooku**?

> *(Vlastnými slovami, jedna-dve vety.)* lebo MacOS je POSIX certifikovany

### 4.4 Vymenuj **2 OS**, ktoré sú POSIX-kompatibilné (okrem Linuxu):

1. MacOS
2. Solaris

### 4.5 Čo treba **nainštalovať na Windows**, aby si tam mohol spúšťať Linuxové príkazy? WSL

---

## Úloha 5 — Orientácia v cudzom systéme

> Predstav si, že ti práve dali SSH prístup na **neznámy server**. Bez toho, aby si **čokoľvek menil**, zisti tieto informácie.

### 5.1 Aká je distribúcia? Spusti:

```bash
cat /etc/os-release | head -3
```

```
NAME="Linux Mint"
VERSION="22.2 (Zara)"
ID=linuxmint
```

### 5.2 Si root alebo bežný používateľ? Spusti `whoami`:

```
student
```

### 5.3 Koľko používateľov má účet v `/home`? Spusti `ls /home`:

```
student
```

### 5.4 Aká verzia jadra beží? Spusti `uname -r`:

```
6.14.0-29-generic
```

### 5.5 **Vlastnými slovami:** aké **3 príkazy** spustíš ako prvé na novom Linuxe, aby si zistil, kde si?

1. pwd
2. ls /
3. whoami

---

## Bonus — interaktívne otázky

### B.1 Skús zistiť, **koľko procesorových jadier** máš:

```bash
nproc
```

Výstup:

```

```

### B.2 Skús `df -h /` — koľko miesta máš na koreňovom disku?

```

```

### B.3 Aký súbor v `/etc` ti **najviac zaujal** a prečo?

---

## Záver

### Z dnešnej hodiny — ktorý adresár si **najlepšie zapamätáš** a prečo?

### Aký bol **najprekvapivejší** poznatok dnešnej hodiny?
