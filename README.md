# File System Overview

Concetto di **File System** , i File System più diffusi e utilizzati con i vari dettagli di questi ultimi.

---

# Comando `mkfs`

Il comando `mkfs` (make filesystem) viene utilizzato per creare un filesystem su una partizione di un dispositivo di memorizzazione.

### Opzioni principali:

1. **-t (tipo di filesystem)**  
   Specifica il tipo di filesystem da creare. Esempi:
   - `mkfs -t ext4 /dev/sdX1` crea un filesystem ext4 sulla partizione `/dev/sdX1`.
   - `mkfs -t ntfs /dev/sdX1` crea un filesystem NTFS sulla partizione `/dev/sdX1`.

2. **-V (verbose)**  
   Abilita l'output verboso, mostrando maggiori dettagli su ciò che sta facendo il comando.
   - Esempio: `mkfs -V ext4 /dev/sdX1`.

3. **-L (label)**  
   Consente di assegnare un'etichetta (label) al filesystem, utile per identificare la partizione.
   - Esempio: `mkfs -t ext4 -L Mariodisk /dev/sdX1` assegna l'etichetta "Mariodisk" al filesystem ext4.

4. **-c (check for bad blocks)**  
   Esegue un controllo dei blocchi danneggiati durante la creazione del filesystem. È utile se si sospetta che il disco possa contenere settori danneggiati. Il comando `mkfs -c` esegue una scansione completa del dispositivo di memorizzazione o della partizione, leggendone ogni settore.
   - Esempio: `mkfs -t ext4 -c /dev/sdX1`.

5. **-b (block size)**  
   Specifica la dimensione del blocco in byte. Questa opzione è utile quando si vuole ottimizzare il filesystem per specifiche esigenze di performance o uso dello spazio.
   - Esempio: `mkfs -t ext4 -b 4096 /dev/sdX1` crea un filesystem ext4 con blocchi di 4096 byte.

6. **-n (no write)**  
   Esegue solo un "dry run" (simulazione) senza effettivamente scrivere il filesystem. Può essere utile per verificare le configurazioni senza rischiare di perdere dati.
   - Esempio: `mkfs -n -t ext4 /dev/sdX1`.

---

# Altri comandi usati

### `lsblk`

Il comando `lsblk` viene utilizzato per visualizzare informazioni sulle partizioni e i dispositivi di memorizzazione nel sistema. Mostra una lista dei dispositivi, delle loro partizioni e dei relativi punti di montaggio. È utile per avere una panoramica dell'architettura dei dischi e delle partizioni.

- Esempio: `lsblk` mostra tutti i dispositivi e le partizioni con una panoramica sulla loro dimensione e tipo.

### `fdisk`

Il comando `fdisk` è uno strumento di gestione delle partizioni per dispositivi di memorizzazione. Permette di creare, eliminare e modificare le partizioni su un disco. È uno strumento utile per configurare i dischi prima di creare un filesystem.

- Esempio: `fdisk /dev/sdX` apre il disco specificato (ad esempio, `/dev/sda`) per la gestione delle partizioni.

---
