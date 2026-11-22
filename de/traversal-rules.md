# Traversal — Spielregeln (Turnierreferenz)

> **Hinweis zur Übersetzung:** Dieses Dokument ist die deutsche Übersetzung des französischen Originals [`traversal-rules.md`](../traversal-rules.md). **Maßgeblich ist die französische Fassung**: Bei Abweichungen oder Auslegungsfragen geht sie dieser Übersetzung vor.
>
> **Geltungsbereich:** ausschließlich die Spielregeln (das Turnierreglement — Paarungen, Zeitplan, Schiedsrichterwesen usw. — wird gesondert behandelt).
> **Konvention:** Mit **⏳ [PB-xx]** gekennzeichnete Stellen verweisen auf einen noch offenen Punkt des Registers.
> Die Bezeichnung „Spieler“ gilt für Personen jeden Geschlechts.

---

## Inhalt

0. [Rangfolge der Quellen](#0-rangfolge-der-quellen)
1. [Überblick und Spielziel](#1-überblick-und-spielziel)
2. [Das Spielbrett](#2-das-spielbrett)
3. [Die Figuren](#3-die-figuren)
4. [Spielaufbau](#4-spielaufbau)
5. [Ablauf eines Zuges](#5-ablauf-eines-zuges)
6. [Bewegung](#6-bewegung)
7. [Kampf](#7-kampf)
8. [Austritt und Wertung](#8-austritt-und-wertung)
9. [Spielende und Sieg](#9-spielende-und-sieg)
10. [Kurzübersicht](#10-kurzübersicht)
11. [Glossar](#11-glossar)

---

## 0. Rangfolge der Quellen

Widersprechen sich die Quellen, gelten sie in folgender Reihenfolge:

1. **die tatsächliche Funktionsweise des Online-Spiels** (technische Umsetzung);
2. **diese Spielregeln**;
3. **die offizielle Seite „Spielanleitung“** auf traversalgame.com.

---

## 1. Überblick und Spielziel

| Element | Wert |
|---|---|
| Spieler | 2 |
| Figuren pro Spieler | 6 (2 von jedem Typ) |
| Spielbrett | Raster aus 10 × 10 Feldern mit unterschiedlichen Höhen |
| Figurentypen | 3 (Kundschafter, Vorhut, Wächter) |

**Spielziel:** die eigenen Figuren über das Spielbrett bewegen und sie **über den Rand gegenüber** der eigenen Startreihe **austreten lassen**. Jede ausgetretene Figur bringt so viele Punkte, wie ihre **Stärke** beträgt.

**Reguläres Spielende:** Sobald **insgesamt zwei Figuren** ausgetreten sind (gleich ob vom selben Spieler oder von verschiedenen Spielern), gewinnt der Spieler mit der höheren Punktzahl.

**Sondersieg:** Ist die **allererste** ausgetretene Figur (beide Spieler zusammengenommen) ein **Wächter**, gewinnt sein Besitzer sofort.

---

## 2. Das Spielbrett

### 2.1 Raster und Koordinaten

- Das Spielbrett ist ein Raster aus **10 × 10** Feldern.
- **Spalten**: **A bis J**, von links nach rechts aus Sicht von Spieler 1 (Rot).
- **Reihen**: **1 bis 10**; Reihe **1** ist die Startreihe von Spieler 1 (unten), Reihe **10** die von Spieler 2 (oben).
- **A1** ist das Feld unten links, **J10** das Feld oben rechts (aus Sicht von Spieler 1).

### 2.2 Höhen

- Jedes Feld hat eine ganzzahlige **Höhe** zwischen **0 und 36** (theoretische Grenzen). In der Praxis liegen zwischen dem niedrigsten und dem höchsten Feld eines Spielbretts etwa 8 bis 10 Einheiten.
- **Geländeregel:** Zwei orthogonal benachbarte Felder unterscheiden sich in der Höhe um höchstens **2 Einheiten**. Kein Feld ist daher unpassierbar.

### 2.3 Erzeugung und Geländemodi

- Jede Partie wird auf einem Spielbrett gespielt, das so erzeugt wird, dass keine Seite einen nennenswerten Vorteil hat.
- Für eine physische Ausgabe kann mit dem **Spielbrett-Generator** der Website ein Spielbrett erstellt werden.
- Vor der Partie kann ein Geländemodus gewählt werden, zum Beispiel:

| Modus | Geländecharakter |
|---|---|
| Zufällig | Ausgewogene Vielfalt an Geländeformen |
| Gebirge | Eindrucksvolle Gipfel in der Mitte |
| Täler | Tiefe Senken, gesäumt von Kämmen |
| Hochland | Gebirge und Täler kombiniert |
| Wald | Überwiegend flach, sanfte Hügel |
| Wüste | Flache Weiten, vereinzelte Gipfel |

> Die Wahl des Modus und die Fairness des Spielbretts regelt das Turnierreglement.

---

## 3. Die Figuren

### 3.1 Eigenschaften

- **Bewegung (B)**: Budget an Bewegungspunkten pro Zug, gleich der **Anzahl der Seiten der Grundfläche** der Figur.
- **Stärke (S)**: Kampfkraft und Punktwert beim Austritt, gleich der **Anzahl der Spitzen oben** auf der Figur.
- Für alle Figuren gilt **B + S = 6**.

| Figur | Form | Bewegung | Stärke | Punkte beim Austritt | Sonderfähigkeit |
|---|---|:-:|:-:|:-:|---|
| **Kundschafter** | Fünfeckiger Kegel | 5 | 1 | 1 | Sonderbewegungen (§ 6.4) |
| **Vorhut** | Rautenförmiger Keil | 4 | 2 | 2 | Sturmangriff: +1 beim Angriff (§ 7.5) |
| **Wächter** | Dreiecksprisma | 3 | 3 | 3 | Sofortiger Sieg, wenn er als erste Figur austritt (§ 9.1) |

---

## 4. Spielaufbau

### 4.1 Seiten

| Spieler | Farbe | Startreihe | Austritt über | Spielt |
|---|---|:-:|---|---|
| Spieler 1 | Rot | 1 | den Rand hinter Reihe 10 | **als Erster** |
| Spieler 2 | Blau | 10 | den Rand hinter Reihe 1 | als Zweiter |

### 4.2 Aufstellen der Figuren

Jeder Spieler stellt seine 6 Figuren auf die Spalten **C bis H** seiner Startreihe:

| Spalte | C | D | E | F | G | H |
|---|---|---|---|---|---|---|
| Figur | Wächter | Vorhut | Kundschafter | Kundschafter | Vorhut | Wächter |

- Spieler 1: **C1 bis H1**.
- Spieler 2: **C10 bis H10**.
- Die Spalten A, B, I und J jeder Startreihe bleiben leer.

```
            A   B   C   D   E   F   G   H   I   J
          ┌───┬───┬───┬───┬───┬───┬───┬───┬───┬───┐
      10  │   │   │ W │ V │ K │ K │ V │ W │   │   │   Spieler 2 (Blau)
          ├───┼───┼───┼───┼───┼───┼───┼───┼───┼───┤
     9…2  │             dazwischenliegende Reihen    │
          ├───┼───┼───┼───┼───┼───┼───┼───┼───┼───┤
       1  │   │   │ W │ V │ K │ K │ V │ W │   │   │   Spieler 1 (Rot)
          └───┴───┴───┴───┴───┴───┴───┴───┴───┴───┘

  W = Wächter   V = Vorhut   K = Kundschafter
  Spieler 1 tritt oben aus (hinter Reihe 10), Spieler 2 unten (hinter Reihe 1).
```

---

## 5. Ablauf eines Zuges

Die Spieler sind abwechselnd am Zug, beginnend mit **Spieler 1**. Wer am Zug ist:

1. wählt **genau eine** seiner Figuren;
2. führt mit dieser Figur **eine Aktion** aus:
   - eine **normale Bewegung** auf ein freies Feld (§ 6.1 bis 6.3);
   - eine **Sonderbewegung**, sofern es sich um einen Kundschafter handelt (§ 6.4);
   - einen **Angriff**: eine Bewegung, deren Zielfeld von einer gegnerischen Figur besetzt ist (§ 7);
   - einen **Austritt vom Spielbrett**, um zu punkten (§ 8);
3. sein Zug **endet** unmittelbar nach dieser Aktion.

**Zugpflicht:** Ein Spieler **muss** in jedem Zug eine regelkonforme Aktion ausführen. Passen ist nicht erlaubt. Nicht genutzte Bewegungspunkte verfallen.

**Kein regelkonformer Zug:** Ein Spieler, der am Zug ist und **keinen regelkonformen Zug** hat (alle seine Figuren sind blockiert, nur verlierende Angriffe wären möglich, oder er hat keine Figur mehr auf dem Spielbrett), **verliert die Partie**.

---

## 6. Bewegung

### 6.1 Grundsatz: Eine Bewegung ist durch ihr Zielfeld bestimmt

- Eine Figur bewegt sich **orthogonal** (vorwärts, rückwärts, links, rechts), Feld für Feld. Diagonal bewegt sie sich nie, außer durch die Sonderbewegung des Kundschafters.
- Eine Bewegung ist ausschließlich durch ihr **Zielfeld** bestimmt. Ein Feld ist **erreichbar**, wenn es einen orthogonalen Weg dorthin gibt,
  - der durch **keine Figur** (eigene oder gegnerische) führt und
  - dessen **Gesamtkosten** (§ 6.2) **kleiner oder gleich** der Bewegung der Figur sind.
- Die Figur darf unterwegs die Richtung wechseln. Der genaue Weg spielt keine Rolle: Es zählen nur die Kosten des günstigsten Wegs zum Zielfeld.
- **Das Zielfeld darf nicht das Ausgangsfeld sein**: Eine Nullbewegung ist verboten. (In einem späteren Zug darf die Figur auf ein zuvor besetztes Feld zurückkehren.)

### 6.2 Kosten eines Schritts

**Kosten eines Schritts = |Höhenunterschied| + 1.** Auf- und Abstieg kosten gleich viel.

| Höhenunterschied | Kosten |
|:-:|:-:|
| 0 (eben) | 1 |
| 1 | 2 |
| 2 | 3 |

**Beispiel** (Weg 2 → 2 → 4 → 3 → 1): 1 + 3 + 2 + 3 = **9 Punkte**.

### 6.3 Übersicht der Verbote

1. Durch eine Figur hindurchziehen, ob eigene oder gegnerische.
2. Die Bewegung auf dem Ausgangsfeld beenden.
3. Auf einem Feld enden, das von einer eigenen Figur besetzt ist.
4. Das Bewegungsbudget überschreiten.

### 6.4 Sonderbewegungen des Kundschafters

In jedem Zug kann ein Kundschafter **anstelle** einer normalen Bewegung **eine** der beiden folgenden Sonderbewegungen ausführen, ausgehend von dem Feld, auf dem er zu Beginn des Zuges steht. Sie verbrauchen keine Bewegungspunkte und **ignorieren das Gelände**.

| Sonderbewegung | Beschreibung | Bedingungen |
|---|---|---|
| **Diagonalschritt** | 1 Feld diagonal | Auch erlaubt, wenn beide angrenzenden orthogonalen Felder besetzt sind |
| **Sprung geradeaus** | 2 Felder in eine orthogonale Richtung | Das **Zwischenfeld muss frei sein** (kein Überspringen einer Figur) |

- Das Zielfeld muss **frei** oder von einer **gegnerischen Figur** besetzt sein; im letzteren Fall ist die Sonderbewegung ein **Angriff** (§ 7).
- Eine Sonderbewegung kann nicht mit einer normalen Bewegung kombiniert werden.
- Mit einer Sonderbewegung kann der Kundschafter das Spielbrett **verlassen** (§ 8.2).

**Beispiel:** Ein orthogonal umstellter Kundschafter (W = Wächter, V = Vorhut, O = freies Feld) kann trotzdem diagonal auf jedes O-Feld ziehen:

```
  O  W  O
  V  K  V
  O  W  O
```

---

## 7. Kampf

### 7.1 Grundsatz

Ein **Angriff** ist eine Aktion, deren **Zielfeld von einer gegnerischen Figur besetzt ist**. Der Angreifer muss zu Beginn des Zuges nicht neben dem Ziel stehen:

- **normale Bewegung:** Das Feld des Ziels muss nach § 6.1 erreichbar sein. Der Schritt **auf das Feld des Ziels** kostet wie jeder andere Schritt |Δh| + 1 und wird auf das Bewegungsbudget angerechnet;
- **Kundschafter:** Auch ein Diagonalschritt oder ein Sprung (§ 6.4) kann auf einer gegnerischen Figur enden.

*Beispiel:* zwei gegnerische Kundschafter auf ebenem Gelände. Kann der erste das Feld des zweiten mit höchstens 5 Bewegungspunkten erreichen, darf er ihn angreifen (Stärke 1 gegen 1: Der Angriff gelingt).

### 7.2 Auflösung

1. Die **effektive Stärke des Angreifers** (§ 7.3) und die des **Verteidigers** (§ 7.4) ermitteln.
2. Vergleichen:
   - **Angreifer ≥ Verteidiger** → Der Verteidiger wird **geschlagen**, endgültig aus dem Spiel entfernt, und **der Angreifer nimmt sein Feld ein**;
   - **Angreifer < Verteidiger** → Der Angriff ist **verboten**: Dieser Zug ist nicht regelkonform.
3. Der Angriff **beendet den Zug**.

> Ein Angriff kann nie scheitern: Nur gewinnende (oder gleichstarke) Angriffe sind regelkonforme Züge.

### 7.3 Effektive Stärke des Angreifers

**Angreifer = Grundstärke + Höhenmodifikator + Verbündete + Sturmangriff (Vorhut)**

Alle Modifikatoren werden **addiert**.

| Modifikator | Bedingung | Wirkung |
|---|---|:-:|
| **Höhe** | Das Feld, auf dem der Angreifer **zu Beginn des Zuges** steht, ist **höher** als das Feld des Ziels | **+1** |
| | … ist **niedriger** als das Feld des Ziels | **−1** |
| | … ist gleich hoch | 0 |
| **Verbündete** | Jede **weitere** Figur des Angreifers, die **orthogonal an das Ziel angrenzt** | **+ ihre Grundstärke** |
| **Sturmangriff** | Nur Vorhut, siehe § 7.5 | **+1** |

- Der Höhenmodifikator beträgt immer **±1**, unabhängig davon, wie groß der Unterschied ist.
- Verglichen wird das Feld zu Beginn des Zuges mit dem Feld des Ziels, nicht das Feld, das unmittelbar vor dem Ziel durchquert wurde.
- Verbündete steuern nur ihre **Grundstärke** bei, ohne Modifikatoren.

### 7.4 Effektive Stärke des Verteidigers

**Verteidiger = Grundstärke + Verstärkung**

| Modifikator | Bedingung | Wirkung |
|---|---|:-:|
| **Verstärkung** | Jede eigene Figur des Verteidigers, die **orthogonal an den Verteidiger angrenzt** | **+1** pro Figur, unabhängig von ihrer Stärke |

Der Verteidiger hat keinen eigenen Höhenmodifikator: Das Gelände wirkt nur über den Modifikator des Angreifers.

### 7.5 Sturmangriff der Vorhut

Eine Vorhut erhält **+1 Angriffsstärke**, wenn — und nur wenn — die **Kosten des günstigsten Wegs** zum Feld des Ziels **genau 4** betragen.

- Die Kosten umfassen den Schritt auf das Feld des Ziels.
- Sie werden auf dem **tatsächlichen Spielbrett** berechnet: Gelände **und** vorhandene Figuren (die den Weg blockieren).
- Der Bonus gilt **automatisch**. Kostet der günstigste Weg 1, 2 oder 3, gibt es keinen Bonus, selbst wenn ein Umweg mit Kosten 4 existiert.

### 7.6 Offizielle Beispiele

**Beispiel 1 — Vorteil der Anhöhe**

| | Angreifer: rote Vorhut | Verteidiger: blaue Vorhut |
|---|:-:|:-:|
| Grundstärke | 2 | 2 |
| Höhe (Zugbeginn höher als das Ziel) | +1 | — |
| Verstärkung (1 blauer Wächter orthogonal angrenzend) | — | +1 |
| **Effektive Stärke** | **3** | **3** |

Ergebnis: 3 ≥ 3 → Die blaue Vorhut wird geschlagen und die rote Vorhut nimmt ihr Feld ein. Ein Wächter als Verstärkung bringt nur +1.

**Beispiel 2 — Gemeinsamer Angriff**

| | Angreifer: roter Kundschafter | Verteidiger: blauer Wächter |
|---|:-:|:-:|
| Grundstärke | 1 | 3 |
| Verbündeter (rote Vorhut orthogonal an das Ziel angrenzend) | +2 | — |
| **Effektive Stärke** | **3** | **3** |

Ergebnis: 3 ≥ 3 → Der blaue Wächter wird geschlagen. Der Kundschafter, der 3 Felder entfernt auf ebenem Gelände startete (Kosten 3 ≤ 5), nimmt sein Feld ein.

---

## 8. Austritt und Wertung

### 8.1 Austritt durch normale Bewegung

- Eine Figur auf ihrer **letzten Reihe** (Reihe 10 für Spieler 1, Reihe 1 für Spieler 2) kann über den Rand gegenüber ihrer eigenen Seite **das Spielbrett verlassen**.
- Der Austritt kostet **immer genau 1 Bewegungspunkt**, unabhängig von der Höhe des Feldes.
- Eine Figur kann die letzte Reihe erreichen, sich darauf bewegen und **im selben Zug** austreten, wenn ihr Budget es erlaubt.
- Der Austritt ist **freiwillig** und **beendet den Zug**.
- Über die seitlichen Ränder oder über den eigenen Startrand kann das Spielbrett nicht verlassen werden.

### 8.2 Austritt des Kundschafters durch Sonderbewegung

Der Kundschafter kann das Spielbrett außerdem verlassen:

- mit einem **Sprung** nach vorn von der vorletzten Reihe (das Zwischenfeld auf der letzten Reihe muss frei sein) oder von der letzten Reihe;
- mit einem **Diagonalschritt** nach vorn von der letzten Reihe.

### 8.3 Punkte

Die ausgetretene Figur wird aus dem Spiel genommen und der Spieler erhält ihre **Grundstärke** als Punkte:

| Figur | Punkte |
|---|:-:|
| Kundschafter | 1 |
| Vorhut | 2 |
| Wächter | 3 |

---

## 9. Spielende und Sieg

Die Bedingungen werden nach jedem Zug geprüft, **in folgender Reihenfolge**.

### 9.1 Sondersieg des Wächters (sofort)

Ist ein **Wächter** die **allererste Figur** der Partie (beide Spieler zusammengenommen), die austritt, **gewinnt** sein Spieler **sofort**. Ist bereits eine andere Figur ausgetreten, bringt der Wächter lediglich 3 Punkte.

### 9.2 Regulärer Sieg (2. ausgetretene Figur)

Sobald die **zweite Figur** der Partie austritt, endet die Partie:

- Punktzahl jedes Spielers = Summe der Grundstärken seiner ausgetretenen Figuren;
- die **höhere Punktzahl** gewinnt;
- bei **Gleichstand** endet die Partie **unentschieden**.

| 1. Austritt | 2. Austritt | Punkte Sp1 – Sp2 | Ergebnis |
|---|---|:-:|---|
| Wächter Sp1 | — | 3 – 0 | Sp1 gewinnt sofort |
| Kundschafter Sp1 | Wächter Sp2 | 1 – 3 | Sp2 gewinnt |
| Vorhut Sp1 | Vorhut Sp2 | 2 – 2 | Unentschieden |
| Kundschafter Sp1 | Vorhut Sp1 | 3 – 0 | Sp1 gewinnt |
| Vorhut Sp1 | Wächter Sp1 | 5 – 0 | Sp1 gewinnt |

### 9.3 Niederlage mangels regelkonformen Zuges

Ein Spieler, der zu Beginn seines Zuges keinen regelkonformen Zug hat, **verliert** (§ 5). Das gilt insbesondere für einen Spieler, der keine Figur mehr auf dem Spielbrett hat.

Diese Regel gilt nur, wenn die Partie weiterläuft. Beendet der Zug, mit dem die letzte Figur eines Spielers vom Brett geht, die Partie (sein Wächter tritt als Erster aus, oder seine Figur ist die 2. ausgetretene), gilt das Ergebnis nach § 9.1 bzw. § 9.2.

*Beispiel:* Spieler 1 hat nur noch einen Wächter, und noch keine Figur ist ausgetreten. Der Wächter tritt aus: Spieler 1 gewinnt sofort (§ 9.1), obwohl er keine Figur mehr hat.

### 9.4 Grenze von 200 Zügen

- Ein **Zug** ist die Aktion eines Spielers. Die Grenze liegt bei **insgesamt 200 Zügen**, also 100 pro Spieler. Die Partie endet nach dem 200. Zug, den Spieler 2 ausführt.
- Löst dieser 200. Zug ein Spielende nach § 9.1 bis 9.3 aus, gilt dieses.
- Andernfalls wird das Ergebnis wie folgt bestimmt:
  1. die **höhere Punktzahl** gewinnt (zu diesem Zeitpunkt ist höchstens eine Figur ausgetreten);
  2. hat **kein Spieler gepunktet**: Es gewinnt der Spieler, dessen am weitesten vorgerückte Figur **ihrem Ziel am nächsten** ist, gemessen in noch zu überquerenden Reihen (ohne Berücksichtigung des Geländes);
  3. bei gleicher Entfernung: Es gewinnt der Spieler, dessen am weitesten vorgerückte Figur die **höhere Stärke** hat ⏳ [PB-24];
  4. bei gleicher Stärke: Die Partie endet **unentschieden**.

**Stellungswiederholung:** Es gibt keine Wiederholungsregel. Hin- und Herziehen, etwa um die Grenze von 200 Zügen zu erreichen, ist eine legitime Strategie.

---

## 10. Kurzübersicht

```
REIHENFOLGE Spieler 1 (Rot, Reihe 1) beginnt · 1 Figur → 1 Aktion → Zugende · Passen verboten
            kein regelkonformer Zug = Niederlage

KOORDINATEN Spalten A–J, Reihen 1–10, A1 unten links (rote Seite)
AUFBAU      C–H: W V K K V W   (Sp1 auf Reihe 1, Sp2 auf Reihe 10)

BEWEGEN     orthogonal · Kosten eines Schritts = |Δh| + 1 · eine Bewegung ist durch ihr Zielfeld bestimmt
            günstigster Weg ≤ B · kein Durchziehen durch Figuren · Zielfeld ≠ Ausgangsfeld

KUNDSCHAFTER (B5 S1)  wahlweise: 1 diagonal (auch zwischen 2 Figuren) ODER Sprung um 2 (Mittelfeld frei)
            Gelände ignoriert · kann damit angreifen und austreten

VORHUT (B4 S2)  +1 beim Angriff, wenn der günstigste Weg (Gelände + Figuren) zum Ziel genau 4 kostet

WÄCHTER (B3 S3)  1. ausgetretene Figur der Partie → sofortiger Sieg

ANGRIFF     = Aktion, die auf einer gegnerischen Figur endet (der letzte Schritt wird bezahlt) · der Angreifer nimmt das Feld ein
            Ang = S + Höhe (Feld bei Zugbeginn vs. Zielfeld: +1 / 0 / −1)
                    + Σ Grund-S der weiteren Verbündeten orthogonal am Ziel + 1 Sturmangriff Vorhut
            Ver = S + 1 pro Verbündetem orthogonal am Verteidiger
            Ang ≥ Ver → geschlagen · Ang < Ver → Zug verboten

AUSTRITT    von der letzten Reihe, feste Kosten 1 · freiwillig · im selben Zug möglich

ENDE        Wächter tritt als 1. aus → Sieg · 2. Figur tritt aus → höhere Punktzahl (Gleichstand = unentschieden)
            200 Züge insgesamt → Punkte > verbleibende Reihen > Stärke > unentschieden
```

---

## 11. Glossar

| Begriff | Definition |
|---|---|
| **Angrenzend** | Orthogonal benachbart: das Feld direkt davor, dahinter, links oder rechts. Diagonalen zählen nicht. |
| **Austrittsrand** | Der Rand des Spielbretts gegenüber der Startreihe eines Spielers, über den seine Figuren zum Punkten austreten. |
| **Bewegung** | Budget an Bewegungspunkten einer Figur für einen Zug. |
| **Effektive Stärke** | Stärke nach Anwendung der Kampfmodifikatoren. |
| **Erreichbares Feld** | Freies oder gegnerisch besetztes Feld, das über einen orthogonalen Weg ohne Durchziehen durch eine Figur zu Gesamtkosten ≤ Bewegung erreicht werden kann. |
| **Grundstärke** | Aufgedruckte Stärke der Figur (1, 2 oder 3), vor allen Modifikatoren. |
| **Letzte Reihe** | Reihe 10 für Spieler 1, Reihe 1 für Spieler 2. |
| **Sturmangriff** | Angriffsbonus +1 der Vorhut (§ 7.5). |
| **Verbündete** | Beim Angriff: die weiteren Figuren des Angreifers, die orthogonal an das Ziel angrenzen. |
| **Verstärkung** | Bei der Verteidigung: eigene Figuren, die orthogonal an den Verteidiger angrenzen (je +1). |
| **Zug** | Aktion eines Spielers, wenn er am Zug ist (Bewegung, Sonderbewegung, Angriff oder Austritt). |
