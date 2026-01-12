# 🧱 Disk Clone Procedure — Eerste Volledige Kloon

Deze handleiding maakt een **volledig identieke kloon** van je actieve Kali-schijf naar een lege backup-schijf.

> ⚠️ **LET OP:**  
> Zorg dat `/dev/sdc` volledig leeg is en **NIET gemount**.  
> *(Cleanup & repair doe je vooraf zelf — perfect.)*

---

## 1️⃣ Controleer de schijven

Voer uit:

```bash
lsblk
---

Verifieer zorgvuldig:

/dev/sda → actieve Kali-schijf

/dev/sdc → lege 1TB backup-schijf

❗ Als deze niet exact kloppen: STOP.

```bash
sudo dd if=/dev/sda of=/dev/sdc bs=64M status=progress conv=noerror,sync
---

⏳ Verwachte tijd: ±1–2 uur

Tijdens het proces wordt elke sector gekopieerd — dit is een bit-perfecte kopie.


Schrijf buffers weg

```bash
sync
---
