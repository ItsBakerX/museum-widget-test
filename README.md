# Museum Widget System 🏛️

Ein responsives Widget-System zur Integration von Museumsobjekten und -sammlungen von museum-digital.org in Ihre Website.

## ⚡ Schnellstart

```html
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" href="./dist/themes/dark.css">
</head>
<body>
    <!-- Einzelobjekt -->
    <div data-md-widget data-mode="object" data-object-id="127" data-width="300"></div>
    
    <!-- Collection mit Suche -->
    <div data-md-widget data-mode="collection" data-collection-id="2" data-width="300"></div>
    
    <script src="./dist/museum-widget.umd.js"></script>
</body>
</html>
```

## 📁 Dateien

| Datei | Beschreibung |
|-------|-------------|
| `demo.html` | **Komplette Demo** - Alle Features und Größen |
| `IMPLEMENTATION_GUIDE.md` | **Detaillierte Anleitung** - Alle Parameter und Optionen |

## 🎯 Features

### Objekt-Widget
- Responsive Schriftgrößen
- Automatisches Bild-Loading mit Fallback
- Click-to-Detail Funktionalität
- Loading & Error States

### Collection-Widget  
- Lokale Echtzeitsuche (debounced)
- Suchvorschläge und Quick-Filter
- Intelligente Pagination
- Zwei-View System (Übersicht → Objektliste)

## 🎨 Themes

```html
<!-- Dark Theme -->
<link rel="stylesheet" href="./dist/themes/dark.css">

<!-- Weitere verfügbare Themes -->
<link rel="stylesheet" href="./dist/themes/default.css">
<link rel="stylesheet" href="./dist/themes/modern.css">
<link rel="stylesheet" href="./dist/themes/museum.css">
```

## 📱 Responsive Design

Schriftgrößen skalieren automatisch mit der Widget-Breite:
- **120px**: 70% Schriftgröße (Minimum)
- **300px**: 100% Schriftgröße (Standard)  
- **500px+**: 150% Schriftgröße (Maximum)

## 🔍 Such-Features

- **Debounced Search**: 500ms Verzögerung nach Eingabe
- **Enter-Taste**: Sofortige Suche
- **Vorschläge**: Materialien, Techniken, Objekttypen
- **Quick-Filter**: Vordefinierte Filter-Buttons
- **Lokale Filterung**: Keine zusätzlichen Server-Anfragen

## 🚀 Demo starten

1. Öffnen Sie `demo.html` im Browser
2. Testen Sie verschiedene Widget-Größen
3. Probieren Sie die Suchfunktion aus
4. Lesen Sie `IMPLEMENTATION_GUIDE.md` für Details

## 📊 Beispiele

```html
<!-- Klein (Mobile) -->
<div data-md-widget data-mode="object" data-object-id="127" data-width="200"></div>

<!-- Standard (Desktop) -->
<div data-md-widget data-mode="object" data-object-id="127" data-width="300"></div>

<!-- Groß (Hero-Bereich) -->
<div data-md-widget data-mode="object" data-object-id="127" data-width="450"></div>

<!-- Collection mit wenigen Objekten pro Seite -->
<div data-md-widget data-mode="collection" data-collection-id="2" data-width="250" data-limit="8"></div>
```

## 🔧 Development

```bash
npm install
npm run build   # Production build
```

## 🔧 Technische Details

- **Quelle**: museum-digital.org API
- **Framework**: React + TypeScript
- **Build**: Vite
- **Browser**: Moderne Browser (ES2015+)
- **Responsive**: Mobile-First Ansatz

---

**Starten Sie mit `demo.html` für eine vollständige Übersicht aller Features! 🎨**
