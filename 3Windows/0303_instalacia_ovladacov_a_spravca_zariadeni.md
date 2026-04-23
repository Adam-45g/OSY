U1

| Kategórie | Názov zariadenia |
|-----------|------------------|
| Grafické adaptéry | NVIDIA GeForce 830M |
| Zvukové vstupy a výstupy | Microphone Array (Realtek Audio), Reproduktory/Slúchadlá (Realtek Audio)
| Sieťové adaptéry | VirtualBox Host-Only Ethernet Adapter, Intel(R) Dual Band Wireless-N 7265, Intel(R) Ethernet Connection (3) I218-LM |
| Diskové jednotky | LITEON LCH-256V2S-11 2.5 7mm 256 GB |

1. -> DESKTOP-M0UTUPT, 10.0
2. -> Intel(R) HD Graphics 5500, 4169 MB
3. -> Reproduktory/Slúchadlá (Realtek Audio)

- informácie z dxdiag a devmgmt.msc nie sú rovnaké
- v dxdiag som našiel viac informácií

U2

| Údaj | Hodnota |
|------|---------|
| Poskytovateľ ovládača | NVIDIA |
| Dátum ovládača | 23.9.2020 |
| Verzia ovládača | 27.21.14.5241 |
| Digitálny podpis | Microsoft Windows Hardware Compatibility Publisher |

- pci\ven_10de&dev_1340&subsys_062b1028

| Údaj | Grafická karta | Zvuková karta |
|------|----------------|---------------|
| Názov | NVIDIA GeForce 830 M | Realtek Audio |
| Verzia ovládača | 27.21.14.5241 | 6.0.1.6105 |
| ID hardvéru | PCI\VEN_10DE&DEV_1340&SUBSYS_062B1028&REV_A2 | HDAUDIO\FUNC_01&VEN_10EC&DEV_0293&SUBSYS_1028062B&REV_1000 |

U3

| Údaj | Hodnota |
|------|---------|
| Stránka výrobcu | nvidia.com/drivers |
| Najnovšia verzia ovládača | 582.28 |
| Veľkosť súboru | 896.76 MB |
| Dátum vydania | streda 28. januára 2026 |

- nainštalovaná verzia: 27.21.14.5241
- najnovšia verzia: 582.28
- áno, je potrebná aktualizácia

U4

| Sekcia | Čo ste našli |
|--------|--------------|
| Plánovač -> Knižnica | 12 úloh |
| Zobrazovač udalostí -> Windows -> Systém | Initialization failed because the driver device could not be created. Use the string "000000000100320000000000D71000C011010000250200C021000000000000000000000000000000" to identify the interface for which initialization failed. It represents the MAC address of the failed interface or the  Globally Unique Interface Identifier (GUID) if NetBT was unable to  map from GUID to MAC address. If neither the MAC address nor the GUID were  available, the string represents a cluster device name. |
| Zdieľané priečinky -> Zdieľanie | 3 zdieľania |
| Lokálni používatelia -> Používatelia | 5 účtov |

- je to rovnaké ako devmgmt.msc
- 2 disky
- 2 oddiely

- nenašiel som rozdiel medzi spustením v devmgmt.msc a compmgmt.msc
