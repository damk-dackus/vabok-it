Challenge 10 – Netwerk virtueel bouwen met Hyper-V (Zuydstad)
=============================================================

In deze Challenge bouw je het netwerk van **Zuydstad Zorgdiensten B.V.** (zie Challenge 9) verder af, maar dan **virtueel**. Je gebruikt **Hyper‑V** om virtuele computers (VM’s) te maken. Zo kun je veilig testen hoe een bedrijfsnetwerk werkt, zonder dat je echte computers nodig hebt.

Je maakt in Hyper‑V een kleine omgeving met:

- een **Windows Server 2025** (fileserver, zoals in Challenge 9);
- een paar **werkstations** (bijvoorbeeld Windows 11) voor de werknemers;
- een **virtueel netwerk** waar alles op aangesloten is.


## Eindproduct

**Je levert een kort verslag in met screenshots van jouw virtuele netwerk.**

In dit verslag:

- **laat je je Hyper‑V omgeving zien** (VM’s en het virtuele netwerk);
- **laat je zien dat de server bereikbaar is** vanaf de werkstations (bijv. ping);
- **laat je zien dat de fileserver werkt** (gedeelde map openen via `\\\\SERVERNAAM\\Share` of via IP);
- **laat je zien dat rechten werken** (wel/niet toegang tot mappen, zoals in Challenge 9);
- **leg je in korte zinnen uit** wat je hebt gemaakt en getest.


## Deel 1 – Voorbereiden (wat ga je bouwen?)

1. Lees Challenge 9 nog een keer. Daarin staan de **mappen**, **rollen** en **rechten**.
2. Bedenk welke VM’s je minimaal nodig hebt. Voor deze Challenge is dit genoeg:
   - 1× **Server**: Windows Server 2025 (fileserver)
   - 2× **Werkstation**: bijvoorbeeld 2 werknemers (bijv. Planner en HR)
3. Maak een eenvoudige planning:
   - eerst VM’s maken en netwerk instellen;
   - daarna IP‑adressen en namen instellen;
   - daarna testen (ping, map openen, rechten controleren).


## Deel 2 – Hyper-V virtueel netwerk maken

1. Open **Hyper‑V Manager**.
2. Maak een **Virtual Switch** (virtuele switch) aan:
   - Gebruik een **Internal** of **Private** switch als je alleen intern wilt testen.
   - Gebruik een **External** switch als je ook internet nodig hebt (alleen als je docent dit wil).
3. Geef de switch een duidelijke naam, bijvoorbeeld: `Zuydstad-LAN`.
4. Zorg dat alle VM’s straks op dezelfde switch aangesloten worden.

> **Tip:** Met een Private/Internal switch kun je veilig oefenen zonder dat je VM’s meteen op het echte netwerk zitten.


## Deel 3 – Virtuele machines maken en installeren

1. Maak een VM voor de **Windows Server 2025**.
   - Geef de VM een naam, bijvoorbeeld `SRV-ZUYDSTAD`.
   - Geef voldoende RAM en opslag (je docent geeft richtlijnen).
   - Koppel de VM aan de switch `Zuydstad-LAN`.
   - Installeer Windows Server 2025 (zoals in Challenge 9).
2. Maak 2 VM’s voor werkstations, bijvoorbeeld:
   - `PC-PLANNING` (Sanne of Yassin)
   - `PC-HR` (Fatima of Jasper)
3. Installeer op de werkstations een besturingssysteem dat je docent aangeeft (bijvoorbeeld Windows 11).
4. Controleer of alle VM’s starten en dat je kunt inloggen.


## Deel 4 – IP-adressen en namen instellen

1. Geef elke VM een **computernaam** die past bij de rol (server en pc’s).
2. Stel IP‑adressen in (of gebruik DHCP als je docent dat wil). Een simpel voorbeeld:
   - Server: `192.168.50.10`
   - PC‑Planning: `192.168.50.20`
   - PC‑HR: `192.168.50.21`
   - Subnetmask: `255.255.255.0`
3. Noteer de IP‑adressen in je verslag.

> **Let op:** Je hoeft geen ingewikkelde DNS of domein te bouwen, tenzij je docent dat vraagt. Het doel is: VM’s kunnen elkaar bereiken en de fileserver werkt.


## Deel 5 – Fileserver en rechten testen (zoals Challenge 9)

1. Maak op de server de gedeelde mapstructuur van Challenge 9 (of gebruik wat je al had).
2. Maak op de server een paar gebruikers en groepen (HR, Planning, enz.).
3. Deel de hoofdmap als **share** en stel **share- en NTFS‑rechten** in.
4. Test vanaf de werkstations:
   - **Ping** de server (bewijs dat het netwerk werkt).
   - Open de share (bijv. `\\\\SRV-ZUYDSTAD\\Zuydstad_Zorgdiensten`).
   - Log in als een HR‑gebruiker en controleer dat HR wel bij HR‑mappen kan.
   - Log in als een planner en controleer dat die niet bij HR‑dossiers kan.
5. Maak van elke test een screenshot voor je verslag.


## Stappenplan in één overzicht

Gebruik onderstaand stappenplan als leidraad. Je mag hiervan afwijken (zie verderop bij *Eigen aanpak mag ook!*), maar zorg dat alle onderdelen uiteindelijk gedaan zijn.

| Stap | Wat doe je?                                                                                   | Voor in het verslag                                                                          |
|------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------|
| 1    | Bepaal welke VM’s je maakt (server + 2 werkstations).                                         | Overzicht van VM’s (namen/rollen).                                                          |
| 2    | Maak een virtuele switch in Hyper‑V (bijv. `Zuydstad-LAN`).                                   | Screenshot van Virtual Switch Manager.                                                       |
| 3    | Maak VM’s aan en installeer Windows Server 2025 + werkstations.                               | Screenshot van Hyper‑V met draaiende VM’s.                                                    |
| 4    | Stel namen en IP‑adressen in.                                                                 | Tabel met IP‑adressen + screenshot van netwerksettings (mag per VM).                         |
| 5    | Configureer fileserver: shares + rechten (share en NTFS).                                     | Screenshot(s) van share en beveiliging/rechten.                                              |
| 6    | Test vanaf werkstations: ping, share openen, wel/niet toegang tot mappen.                     | Screenshots van ping + map openen + toegang geweigerd/toegestaan.                            |
| 7    | Maak het verslag af en lever het in.                                                          | PDF met alle screenshots en korte uitleg.                                                    |


## Eigen aanpak mag ook!

Dit stappenplan helpt je op weg, maar je hoeft het niet precies zo te doen. Misschien maak je meer werkstations, of voeg je extra onderdelen toe (zoals een extra switch of een test‑pc). Dat is prima!

**Belangrijk is dat:**

- je in Hyper‑V een **virtueel netwerk** hebt gemaakt;
- er minimaal een **Windows Server 2025** als fileserver is;
- werkstations de server kunnen bereiken (ping);
- je kunt laten zien dat de **gedeelde mappen en rechten** werken;
- je dit bewijst met duidelijke screenshots in een verslag.


## Beoordeling – Rubric Virtualiseren met Hyper-V

Je docent gebruikt onderstaande rubric om jullie werk te beoordelen.

| Aspect                         | 0 punten (onvoldoende)                                                       | 1 punt (voldoende)                                                                 | 2 punten (goed)                                                                                          |
|--------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| Hyper‑V omgeving               | VM’s of virtueel netwerk ontbreken; omgeving werkt niet.                     | VM’s draaien en netwerk is er, maar onvolledig of onduidelijk ingericht.          | VM’s draaien netjes; virtuele switch en netwerk zijn duidelijk en logisch ingericht.                     |
| Netwerk en bereikbaarheid      | VM’s kunnen niet met elkaar communiceren; server niet bereikbaar.             | Basisbereikbaarheid werkt, maar niet altijd of niet goed aangetoond.              | Werkstations bereiken de server (ping/verbinding) en dit is duidelijk getest en vastgelegd.              |
| Fileserver en rechten          | Share/rechten werken niet; iedereen kan alles of niemand kan erbij.           | Share werkt, maar rechten zijn deels fout of niet goed getest.                     | Share + rechten werken zoals in Challenge 9; wel/niet toegang is getest vanaf werkstations.              |

**Beoordeling:**

- **Maximumscore**: 6 punten  
- **Suggestie normering**:  
  - 5–6 punten: goed  
  - 3–4 punten: voldoende  
  - 0–2 punten: onvoldoende


## Inleveren

Ben je klaar met de opdracht?

1. Controleer of alle screenshots duidelijk zijn en of je uitleg klopt.  
2. Lever je verslag in volgens de afspraken (bijvoorbeeld via NNNext of de ELO).  
Pas als dit gedaan is, is Challenge 10 volledig afgerond.

