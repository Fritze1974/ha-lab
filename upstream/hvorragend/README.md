# 📦 Upstream: Hvorragend

> [!WARNING]
> **Nur Referenz – nicht bearbeiten und nicht importieren!**
> Die Dateien in diesem Ordner sind unveränderte Kopien der Originale. Die deutsche Fassung zum Importieren liegt unter [`blueprints/`](../../blueprints/).

**Quelle:** [github.com/hvorragend/ha-blueprints](https://github.com/hvorragend/ha-blueprints)
**Autor:** Hvorragend – alle Rechte am Original liegen beim Autor.

| Original | Deutsche Fassung |
|---|---|
| [`cover_control_automation.yaml`](cover_control_automation.yaml) | [`blueprints/cover_control_automation_de.yaml`](../../blueprints/cover_control_automation_de.yaml) |


______________________________________________________________________________________________________________________________________________

# :information_source: Interne Bearbeitungsanleitung #
______________________________________________________________________________________________________________________________________________


## 🔄 Ablauf bei einem Update

### 1. Original aktualisieren

Neue Version aus dem Original-Repository 1:1 hierher kopieren und **allein** committen – keine anderen Dateien im selben Commit:

```bash
git commit -m "upstream: CCA auf Version X aktualisiert" upstream/hvorragend/cover_control_automation.yaml
```

### 2. Änderungen ansehen

Der Diff dieses Commits ist die To-do-Liste für die deutsche Fassung:

```bash
git show HEAD -- upstream/hvorragend/cover_control_automation.yaml
```

Alternativ den Commit auf GitHub öffnen.

### 3. In die deutsche Fassung übernehmen

Änderungen in `blueprints/cover_control_automation_de.yaml` einpflegen, neue Texte übersetzen, den Versionshinweis im Dateikopf anpassen und separat committen:

```bash
git commit -m "de: Änderungen aus upstream Version X übernommen" blueprints/cover_control_automation_de.yaml
```

### 4. Kontrolle

Beide Dateien sollten sich nur noch in übersetzten Texten unterscheiden:

```bash
git diff --no-index --word-diff upstream/hvorragend/cover_control_automation.yaml blueprints/cover_control_automation_de.yaml
```

Alles, was dort erscheint und **kein** übersetzter Text ist (Bedingungen, neue Inputs, Defaults, Selektoren), wurde noch nicht übernommen.

---

## ✅ Checkliste für die deutsche Fassung

- [ ] Versionshinweis im Dateikopf aktualisiert (`# Übersetzung basiert auf: …`)
- [ ] `source_url` zeigt auf die eigene Datei:
      `https://github.com/Fritze1974/ha-lab/blob/main/blueprints/cover_control_automation_de.yaml`
- [ ] Neue Eingabefelder und Beschreibungen übersetzt
- [ ] Kontroll-Diff zeigt nur noch Textunterschiede
- [ ] In Home Assistant testweise neu importiert