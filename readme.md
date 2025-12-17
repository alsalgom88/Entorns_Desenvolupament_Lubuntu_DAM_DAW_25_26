# 🖥️ Entorns de Desenvolupament — Lubuntu (DAM / DAW 2025-2026)

Màquina virtual basada en **Lubuntu (Ubuntu lleuger)** preparada com a **entorn de treball homogeni** per a l’alumnat dels cicles **DAM i DAW** del curs **2025-2026**.

L’objectiu d’aquesta màquina és garantir que tot l’alumnat treballi amb el **mateix entorn**, evitant problemes de compatibilitat entre sistemes operatius.

---

## 🔐 Credencials d’accés

* **Usuari:** `usuario`
* **Contrasenya:** `usuario`

---

## 🐧 Sistema operatiu

* **Distribució:** Lubuntu (Ubuntu-based)
* **Arquitectura:** 64 bits
* **Entorn gràfic:** LXQt (lleuger i ràpid)

---

## ⚙️ Configuració de la màquina virtual

* **Memòria RAM:** 4 GB
* **Processadors:** 2 CPU
* **Disc dur:** Dinàmic (VDI)
* **Guest Additions:** instal·lades
* **Arrencada:** Disc dur

---

## 🌐 Configuració de xarxa (IMPORTANT)

La màquina té **DUES interfícies de xarxa** configurades:

### 🔹 Adaptador 1 — NAT

* Permet accés a **Internet**
* Funciona sense configuració addicional
* Necessari per:

  * actualitzar el sistema
  * instal·lar paquets
  * navegar

### 🔹 Adaptador 2 — Pont (Bridged)

* La màquina obté **IP pròpia dins de la xarxa**
* Permet:

  * connexions **SSH**
  * serveis locals
  * pràctiques de xarxa i servidor
* Ideal per treballar amb:

  * Odoo
  * servidors web
  * APIs
  * bases de dades

📌 **No desactivar cap dels dos adaptadors**

---

## 📦 Descàrrega de la màquina (OVA)

📁 **Google Drive (OVA oficial):**
👉 [https://drive.google.com/drive/folders/1R7MXkldDcafluON1YybpkK79HE6DBIXq?usp=sharing](https://drive.google.com/drive/folders/1R7MXkldDcafluON1YybpkK79HE6DBIXq?usp=sharing)

Descarrega el fitxer **.ova** complet abans d’importar-lo.

---

## 🧰 Requisits previs

### ✔ VirtualBox

* **Versió recomanada:** 7.x
* Incloure **Extension Pack** de la mateixa versió

🔗 [https://www.virtualbox.org/](https://www.virtualbox.org/)

---

## ▶️ Instal·lació a Windows

1. Instal·la **VirtualBox** i l’**Extension Pack**
2. Obre VirtualBox
3. Ves a **Fitxer → Importa un servei virtualitzat**
4. Selecciona el fitxer `.ova` descarregat
5. Accepta la configuració per defecte
6. Importa la màquina
7. Inicia-la amb **Iniciar**

📌 Si el rendiment és baix, comprova:

* virtualització activada a la BIOS
* Hyper-V desactivat

---

## ▶️ Instal·lació a Ubuntu / Linux

1. Instal·la VirtualBox:

```bash
sudo apt update
sudo apt install virtualbox
```

2. Instal·la l’Extension Pack corresponent
3. Obre VirtualBox
4. **File → Import Appliance**
5. Selecciona el fitxer `.ova`
6. Importa i inicia la màquina

📌 Assegura’t de tenir permisos de virtualització (`kvm-ok`).

---

## 🖥️ Ús bàsic de la màquina

1. Inicia la màquina virtual
2. Inicia sessió amb:

   * usuari: `usuario`
   * contrasenya: `usuario`
3. Treballa normalment amb:

   * terminal Linux
   * eines de desenvolupament
   * pràctiques de DAM / DAW

---

## 🧯 Errors freqüents i Troubleshooting

Aquesta secció recull els problemes més habituals durant la importació i l’ús de la màquina virtual i com solucionar-los.

---

### ❌ La màquina no arrenca / pantalla negra

**Possible causa:**

* Virtualització desactivada a la BIOS
* Conflicte amb Hyper-V (Windows)

**Solució (Windows):**

1. Reinicia l’ordinador i entra a la BIOS
2. Activa:

   * Intel VT-x / AMD-V
3. A Windows:

   * Desactiva **Hyper-V**
   * Desactiva **Plataforma de màquina virtual**
   * Desactiva **Windows Hypervisor Platform**
4. Reinicia l’ordinador

---

### ❌ Rendiment molt lent

**Possible causa:**

* Poca RAM assignada
* Virtualització inactiva

**Solució:**

* Assegura’t que la VM té **4 GB de RAM**
* Tanca aplicacions pesades al sistema host
* Comprova que la virtualització està activada

---

### ❌ No hi ha connexió a Internet

**Possible causa:**

* Adaptador NAT desactivat
* Xarxa modificada

**Solució:**

1. Apaga la màquina
2. Ves a **Configuració → Xarxa**
3. Comprova:

   * Adaptador 1 → **NAT**
   * Adaptador 2 → **Pont (Bridged)**
4. Torna a iniciar la màquina

---

### ❌ No puc accedir per SSH / no té IP a la xarxa

**Possible causa:**

* Adaptador en pont mal configurat
* Xarxa incorrecta seleccionada

**Solució:**

1. Configuració → Xarxa → Adaptador 2
2. Mode: **Pont**
3. Targeta: la del teu ordinador (Wi-Fi o Ethernet)
4. Reinicia la VM
5. Comprova IP amb:

```bash
ip a
```

---

### ❌ Error en importar l’OVA

**Possible causa:**

* Descàrrega incompleta o corrupta
* Versió antiga de VirtualBox

**Solució:**

* Torna a descarregar l’OVA
* Actualitza VirtualBox a la versió **7.x**
* Importa de nou el fitxer

---

### ❌ Resolució de pantalla petita o incorrecta

**Possible causa:**

* Guest Additions no actives

**Solució:**

* Comprova que **Guest Additions** estan instal·lades
* A VirtualBox:

  * Visualitza → **Escala automàtica**
  * Pantalla → **VMSVGA**

---

### ❌ El ratolí queda “capturat”

**Solució:**

* Prem la tecla **Ctrl dret** per alliberar el ratolí

---

### ❌ No puc copiar/enganxar entre host i VM

**Solució:**

1. Apaga la màquina
2. Configuració → General → Avançat
3. Porta-retalls:

   * **Bidireccional**
4. Reinicia la VM

---

### ❌ Errors amb permisos (apt, instal·lacions)

**Solució:**

* Executa comandes amb `sudo`
* Usuari `usuario` té permisos d’administrador

---

### ❌ Conflictes de xarxa amb VPN

**Possible causa:**

* VPN activa al sistema host

**Solució:**

* Desconnecta la VPN abans d’iniciar la màquina
* Especialment important amb xarxa en pont

---

### 🆘 Encara no funciona?

Abans de demanar ajuda:

1. Reinicia la màquina virtual
2. Comprova la configuració de xarxa
3. Verifica la virtualització
4. Revisa aquesta secció

Si el problema persisteix:

* Adjunta **captura d’error**
* Indica **sistema host (Windows / Ubuntu)**
* Explica **què estaves fent**

---

🧠 *“Have you tried turning it off and on again?”* — *The IT Crowd* 😄
---

## 🔐 Connexió per IP i ús per SSH

Aquesta màquina virtual permet treballar **tant en mode gràfic com per consola**, gràcies a la configuració de xarxa amb **NAT + Pont**.

---

## 🌐 Com veure la IP de la màquina virtual

### 🔹 Opció 1 — Des del terminal (recomanat)

1. Obre el **Terminal** dins de Lubuntu
2. Executa:

```bash
ip a
```

3. Busca una interfície del tipus `enp0s8` o `eth1`
4. L’adreça IP apareix com:

```
inet 192.168.x.x
```

📌 Aquesta és la IP que s’utilitzarà per a **SSH**.

---

### 🔹 Opció 2 — Comanda simplificada

```bash
hostname -I
```

Mostra directament la IP assignada.

---

## 🔑 Connexió per SSH (des de l’ordinador host)

### ✔ Des de Linux / macOS

Obre un terminal al teu ordinador i executa:

```bash
ssh usuario@IP_DE_LA_VM
```

Exemple:

```bash
ssh usuario@192.168.1.120
```

Introdueix la contrasenya:

```
usuario
```

---

### ✔ Des de Windows (PowerShell o Terminal)

A Windows 10/11:

1. Obre **PowerShell** o **Terminal**
2. Executa:

```powershell
ssh usuario@IP_DE_LA_VM
```

3. Accepta la clau si és el primer cop
4. Introdueix la contrasenya

📌 **No cal PuTTY**, Windows ja inclou SSH.

---

## 🖥️ Treballar només per consola

Un cop connectat per SSH:

* No cal entorn gràfic
* Ideal per:

  * servidors
  * Docker
  * Odoo
  * desenvolupament backend
  * pràctiques d’entorns

---

## 📦 Instal·lar programari per consola

### 🔹 Actualitzar el sistema

```bash
sudo apt update
sudo apt upgrade
```

---

### 🔹 Instal·lar paquets

```bash
sudo apt install nom_del_paquet
```

Exemples:

```bash
sudo apt install git
sudo apt install curl
sudo apt install docker.io
```

---

### 🔹 Comprovar serveis

```bash
systemctl status servei
```

Exemple:

```bash
systemctl status ssh
```

---

## 🔄 Reiniciar serveis

```bash
sudo systemctl restart ssh
```

---

## 📁 Transferència de fitxers (SCP)

Des del teu ordinador host:

```bash
scp fitxer.txt usuario@IP_DE_LA_VM:/home/usuario/
```

---

## 🧪 Comprovar la connexió de xarxa

```bash
ping google.com
```

Si respon, la connexió funciona correctament.

---

## 🔒 Notes de seguretat (docents)

* Usuari i contrasenya són **genèrics** (ús educatiu)
* No exposar la VM a Internet
* Canviar credencials només si s’indica

---

🧠 *“Real developers don’t fear the terminal.”* 😄
---

## 🔧 Recomanacions

* No modificar la configuració de xarxa
* No canviar usuari ni contrasenya
* Utilitzar aquesta màquina per:

  * pràctiques d’entorns
  * servidors
  * desenvolupament
  * proves

---

## 📚 Context educatiu

Màquina utilitzada a l’aula dins dels mòduls:

* **Entorns de Desenvolupament**
* **Programació**
* **Desenvolupament Web**
* **Aplicacions Multiplataforma**

---

🧠 *“It works on my machine” deixa de ser una excusa quan tots feu servir la mateixa.* 😄
