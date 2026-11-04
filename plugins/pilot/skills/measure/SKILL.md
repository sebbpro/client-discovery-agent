---
name: measure
description: Messprotokoll für Pilotanwendungen — hält je Anwendungsfall fest, wie lange die Aufgabe vorher dauerte, wie lange sie mit KI dauert und wie viel nachgearbeitet werden musste, und erzeugt eine Zusammenfassung, die die Pilotnutzerin oder der Pilotnutzer prüft und an sebb.pro schickt. Use when the user says "Messung starten", "Pilot messen", "Zeit festhalten", "Messprotokoll", or "log pilot results". Beispiel-Skill für die Phase Pilot (Entwurf).
---

# Pilot — Messprotokoll

Ein kurzer, wiederholbarer Ablauf (ca. 3 Minuten pro Eintrag), mit dem Pilotnutzer festhalten, was
die KI-Anwendung in der Praxis bringt. Am Ende steht ein **Messprotokoll, das Sie vor dem Senden
prüfen**. Die Bewertung macht sebb.pro.

Status: Beispiel-Entwurf für die Phase Pilot; Ablauf und Fragen sind noch nicht erprobt.

Speak to the person in the formal "Sie". This skill only **records**; it never extrapolates savings,
ranks use cases or recommends a roll-out.

## Non-negotiables

1. **Zahlen so, wie sie genannt werden.** Mark every figure as `gemessen` or `geschätzt`. Never
   compute savings per year, per person or in money — that is done on the sebb.pro side.
2. **Keine Inhalte, nur Art und Aufwand.** No project content, personal data or documents. If pasted,
   stop, say once why, and record only the abstract version.
3. **Rollen, keine Personen.** Record the role of the pilot user, not a name.
4. **Max. 3 Fragen pro Nachricht**, via `AskUserQuestion`, 2–4 real options for this use case,
   free text always possible. Write the person's answer, not the option label.
5. **Nichts wird gesendet.** The skill produces a protocol the person reviews and forwards.
6. **Never ask them to grade the skill.** Close by offering, not by requesting feedback.

## Ablauf pro Eintrag

1. **Anwendungsfall:** Which task was this? If a discovery summary (`format: ai-discovery-intake/1`)
   is available, offer its listed tasks as options; otherwise ask in their words.
2. **Vorher:** How long does the task usually take without AI, and is that measured or estimated?
3. **Mit KI:** How long did it take this time (including checking), how much had to be corrected
   (kaum / mittel / viel), and was the result usable as is?

Optional after the third entry for the same use case: a one-line note on what worked or not.

## Keeping state

- **With file access:** append to `messprotokoll.md` in the open folder, using
  `assets/messprotokoll.de.md`. A dropped session loses nothing.
- **Without file access:** keep the running protocol in the conversation and post it as a copyable
  block after every third entry; on resume ("weiter mit der Messung") read such a block.

## Final: review and handover

Show the complete protocol and say plainly: *This is exactly what would go to sebb.pro.* Ask once
(`AskUserQuestion`): "So absenden" / "Etwas ändern". Hand over as file, private artifact or copyable
block, whichever is available, and close with an offer: "Was möchten Sie noch wissen — oder soll ich
sagen, was als Nächstes passiert?" Do not promise results.
