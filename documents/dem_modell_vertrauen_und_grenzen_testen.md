# Dem Modell vertrauen und Grenzen testen – Prompt Engineering als Erkundung

## 1. Iteration ist der Kern, nicht Perfektion beim ersten Versuch

Das Gespräch mit einem Modell unterscheidet sich von menschlicher Kommunikation durch den Neustart-Knopf: Du kannst jederzeit zurück auf Null, komplett neu beginnen, ohne Interferenz zwischen Versuchen. Diese Fähigkeit zum sauberen Experimentieren ist die Grundlage für echtes Prompt Engineering. Schreibe einen Prompt, führe ihn aus, lies das Ergebnis bewusst, präzisiere, wiederhole. In 15 Minuten können hunderte Prompts entstehen – das ist normal und richtig.

**Das Prinzip:**
Perfektion beim ersten Versuch ist weder möglich noch nötig. Der iterative Prozess selbst bringt die Verbesserung.

## 2. Lies die Modell-Ausgaben aktiv – dort liegt das Lernen

Wie Datenwissenschaftler ihre Daten anschauen müssen, musst du Modell-Outputs aktiv lesen. Nicht nur das Endergebnis bewerten, sondern verstehen, wie das Modell denkt, wo es abbiegt, was es missverstanden hat. Hunderte von Ausgaben durchlesen ist keine Zeitverschwendung, sondern die schnellste Methode zu lernen, was tatsächlich funktioniert. Jede unerwartete Antwort ist eine Lerngelegenheit, kein Fehler.

**Praktisch:**
Nimm dir Zeit, Modell-Outputs wirklich zu lesen – nicht nur zu überfliegen. Das Muster erkennen, nicht nur das Ergebnis abhaken.

## 3. Teste Edge Cases systematisch, nicht nur typische Fälle

Der klassische Fehler: Prompt am typischen Fall testen, sehen dass es funktioniert, fertig. In Wahrheit brauchst du die Randfälle – leere Eingaben, fehlende Daten, Tippfehler, keine Großschreibung, keine Satzzeichen. Nutzer denken, es ist Google. Sie tippen unvollständige Sätze ohne Frage. Dein Prompt muss für diese Realität gebaut sein, nicht für deine idealisierten Testfälle.

**Konkret zu testen:**
- Leere Eingabe
- Daten fehlen komplett
- Ungültige Formate
- Chaos-Eingaben (wie echte Nutzer schreiben)

## 4. Klare Kommunikation schlägt clevere Tricks

Prompt Engineering ist im Kern klares Sprechen. Wie du einer kompetenten, aber kontextfremden Person eine Aufgabe erklären würdest: Worum geht es? Was soll konkret getan werden? Welche Sonderfälle können auftreten? Keine Rollen-Inszenierung ("Du bist Großmeister X"), keine abstrakten Metaphern. Ehrlicher Kontext, präzise Aufgabenbeschreibung, klare Erwartungen.

**Vermeide:**
Fantasievolle Rollen ohne konkrete Relevanz zur Aufgabe. Setze stattdessen auf ehrliche, klare Beschreibungen.

## 5. Vertraue den Fähigkeiten des Modells – unterschätze sie nicht

Modelle sind inzwischen stark genug für komplexe Problemzusammenhänge. Vereinfache nicht aus Angst. Gib dem Modell alle nötigen Informationen, den vollen Kontext, die Quellen, die Papers. Modelle können viel mehr tragen, als die meisten Menschen annehmen. Die Tendenz zu vereinfachen und zu verstecken ist kontraproduktiv – das Modell braucht Kontext, um intelligent zu antworten.

**Haltung:**
Vertrauen in die Fähigkeit des Modells, Komplexität zu tragen. Keine Angst vor Länge, Kontext oder Präzision.

## 6. Teste an der Grenze: Aufgaben, die das Modell fast kann

Wo lernst du am meisten? Dort, wo das Modell fast erfolgreich ist, aber noch nicht ganz. Stelle Aufgaben, von denen du glaubst, dass das Modell sie knapp schaffen könnte. Diese Grenze zu erkunden – nicht sicher zu scheiternde Aufgaben, nicht trivial lösbare, sondern die Zone dazwischen – zeigt dir die wahren Fähigkeiten und Limitierungen.

**Experimentiere:**
Mit Aufgaben, die gerade an der vermuteten Leistungsgrenze liegen. Dort entdeckst du Überraschungen.

## 7. Beziehe das Modell in die Selbstkorrektur ein

Wenn das Modell einen Fehler macht, nutze es als Lernpartner: "Das war falsch wegen X. Kannst du analysieren, warum du es falsch gemacht hast, und meine Anweisungen so überarbeiten, dass du es künftig richtig machen würdest?" Das Modell liefert oft selbst die Verbesserung des Prompts. Es kann reflektieren und Vorschläge machen – nutze diese Fähigkeit aktiv.

**Dialog statt Monolog:**
Das Modell ist nicht nur Ausführer, sondern Partner im Prompt-Verbesserungsprozess.

## 8. Behandle Prompts wie Code – versioniere, tracke, experimentiere

Prompts sind natürlichsprachlicher Code. Versionskontrolle, Experimentverfolgung, präzises Management sind genauso wichtig wie bei klassischem Code. Du musst wissen, wie der Prompt vor drei Iterationen aussah, welches Experiment welches Ergebnis brachte. Ohne Tracking verlierst du den Überblick. Prompts sind Artefakte, die strukturiertes Management verdienen.

**Werkzeuge:**
Git für Prompts, systematisches Logging von Experimenten, klare Benennung von Versionen.

## 9. Plane Fehlertoleranz und Unsicherheit ein

Erlaube dem Modell, Unsicherheit zu markieren. Wenn du einen Tag einfügst wie "Wenn du dir unsicher bist, schreibe <unsure> und erkläre kurz warum", erhöhst du die Datenqualität drastisch. Verhindere falsche Sicherheit. Das Modell soll nicht raten, sondern ehrlich sagen, wenn es nicht sicher ist.

**Beispiel:**
```
Wenn du dir unsicher bist, markiere mit <unsure> und erkläre, warum die Information unklar ist.
```

## 10. Denke in Systemen, nicht nur in einzelnen Prompts

Prompt Engineering endet nicht beim Text. Wo kommen die Daten her? Welche Daten sind verfügbar? Wie fügt sich der Prompt in den größeren Workflow ein? Latenz-Trade-offs, Datenmenge, Integration mit anderen Systemen – all das gehört dazu. Der Prompt ist Teil eines Gesamtsystems, und dieses System zu durchdenken ist genauso wichtig wie den Text selbst zu formulieren.

**System-Fragen:**
- Welche Daten hat das Modell Zugriff?
- Wie ist Latenz vs. Qualität abgewogen?
- Wo im Workflow sitzt dieser Prompt?

---

> Prompt Engineering ist keine Kunstform mit Geheimtricks – es ist systematisches Erkunden der Grenzen durch klare Kommunikation und unermüdliches Experimentieren.

---

**Diskussionsteilnehmer:** Alex Albert (Developer Relations Lead), Zack Witten (Prompt Engineer), Amanda Askell (Finetuning Team Lead), David Hershey (Solutions Architect)

---

#author: Anthropic

#published: September 2024

#source: https://www.youtube.com/watch?v=T9aRN5JkmL8

#background: Founded in 2021 by former OpenAI researchers Dario and Daniela Amodei, Anthropic emerged from concerns about AI safety. The company invested heavily in constitutional AI research and interpretability before scaling, creating a culture valuing safety testing and transparent communication. Known for Claude, it maintains its founding commitment to responsible AI deployment.

#decade: #2020s
