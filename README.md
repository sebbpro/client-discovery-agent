# sebbpro-ai

Skills von sebb.pro, die Kunden in ihrem eigenen Claude-Account nutzen. Ein Marketplace, ein Plugin
pro Projektphase, jedes Plugin mit einem oder mehreren Skills.

| Plugin (Phase) | Skill | Aufruf | Zweck |
|---|---|---|---|
| `sebbpro-discovery` | `intake` | `/sebbpro-discovery:intake` | Vorbereitungsinterview für die KI-Einführung (ca. 30 Min.); Ergebnis ist eine Zusammenfassung, die Sie prüfen und an sebb.pro schicken |
| `sebbpro-pilot` _(Beispiel, Entwurf)_ | `measure` | `/sebbpro-pilot:measure` | Messprotokoll für Pilotanwendungen: Zeit vorher/mit KI und Nacharbeit je Anwendungsfall |

## Installation (Claude Code)

Marketplace einmal hinzufügen, danach pro Phase das passende Plugin installieren:

```
/plugin marketplace add sebbpro/sebbpro-ai
/plugin install sebbpro-discovery@sebbpro-ai-marketplace
```

Danach `/sebbpro-discovery:intake` oder einfach „Discovery starten“. Für die Pilotphase entsprechend
`/plugin install sebbpro-pilot@sebbpro-ai-marketplace`.
