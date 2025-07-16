# Museum Widget Implementierungsanleitung

## 📋 Überblick

Das Museum Widget System bietet eine einfache Möglichkeit, Museumsobjekte und -sammlungen von museum-digital.org in Ihre Website zu integrieren. Es unterstützt responsive Design, lokale Suche und verschiedene Darstellungsmodi.

## 🚀 Schnellstart

### 1. Dateien einbinden

```html
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- CSS Theme einbinden -->
    <link rel="stylesheet" href="./dist/themes/dark.css">
</head>
<body>
    <!-- Ihre Widgets hier -->
    
    <!-- JavaScript am Ende -->
    <script src="./dist/museum-widget.umd.js"></script>
</body>
</html>
```

### 2. Widget hinzufügen

```html
<!-- Einzelobjekt -->
<div data-md-widget data-mode="object" data-object-id="127" data-width="300"></div>

<!-- Collection mit Suche -->
<div data-md-widget data-mode="collection" data-collection-id="2" data-width="300" data-limit="12"></div>
```

## 📊 Widget-Typen

### Objekt-Widget
Zeigt ein einzelnes Museumsobjekt an.

**HTML:**
```html
<div data-md-widget 
     data-mode="object" 
     data-object-id="127" 
     data-width="300">
</div>
```

**Parameter:**
- `data-mode="object"` - Widget-Typ
- `data-object-id="123"` - ID des Objekts
- `data-width="300"` - Breite in Pixeln (Standard: 300)

**Features:**
- ✅ Automatisches Laden von museum-digital.org
- ✅ Responsive Bilder mit Fallback
- ✅ Dynamische Schriftgrößen
- ✅ Loading & Error States
- ✅ Click-to-Detail Funktionalität

### Collection-Widget
Zeigt eine Sammlung mit Suchfunktion an.

**HTML:**
```html
<div data-md-widget 
     data-mode="collection" 
     data-collection-id="2" 
     data-width="300" 
     data-limit="12">
</div>
```

**Parameter:**
- `data-mode="collection"` - Widget-Typ
- `data-collection-id="2"` - ID der Collection
- `data-width="300"` - Breite der Collection und Objekt Widgets (Standard: 300)
- `data-limit="12"` - Objekte pro Seite (Standard: 24)

**Features:**
- Zwei Ansichten: Collection-Übersicht → Objektliste
- Lokale Echtzeitsuche (debounced, 500ms)
- Suchvorschläge und Quick-Filter
- Intelligente Pagination
- Loading aller Objekte
- Responsive Grid-Layout

## 🎨 Verfügbare Themes

### Dark Theme
```html
<link rel="stylesheet" href="./dist/themes/dark.css">
```
- Dunkler Hintergrund (#2c2c2c)
- Blaue Akzentfarbe (#00a8ff)
- Optimiert für moderne Websites

### Standard Theme
```html
<link rel="stylesheet" href="./dist/themes/default.css">
```
- Heller Hintergrund
- Klassisches Design
- Gute Lesbarkeit

### Modern Theme
```html
<link rel="stylesheet" href="./dist/themes/modern.css">
```
- Minimalistisches Design
- Viel Weißraum

### Museum Theme
```html
<link rel="stylesheet" href="./dist/themes/museum.css">
```
- Klassische Museumsoptik
- Elegante Farbgebung

## 📱 Responsive Verhalten

### Mobile Optimierungen
- Touch-freundliche Button-Größen
- Stapelbare Layouts bei schmalen Bildschirmen
- Angepasste Suchkomponenten

## 🔍 Such-Funktionen

### Automatische Suche
- **Debounced**: 500ms Verzögerung nach Eingabe-Ende
- **Enter-Taste**: Sofortige Suche
- **Echtzeitfilterung**: Lokale Objektsuche ohne Server-Anfragen

### Suchvorschläge
Vordefinierte Begriffe für häufige Suchbegriffe:
- Materialien: Fotografie, Keramik, Holz, Metall, Glas, Textil
- Objekttypen: Münze, Medaille, Gemälde, Skulptur, Dokument

### Quick-Filter
Schnelle Filter-Buttons für:
- Bilder
- Dokumente  
- Keramik
- Metall

## 🔧 Fehlerbehebung

### Häufige Probleme

**Widget lädt nicht:**
- Prüfen Sie, ob `museum-widget.umd.js` korrekt eingebunden ist
- CSS-Datei muss vor dem JavaScript geladen werden
- Objekt-/Collection-IDs müssen gültig sein

**Styling-Probleme:**
- Nur ein Theme zur Zeit verwenden
- `data-width` Parameter anpassen

**Responsive-Probleme:**
- `viewport` Meta-Tag prüfen
- CSS-Konflikte mit eigenem Stylesheet vermeiden

## 📈 Performance-Tipps

### Best Practices
```html
<!-- ✅ Gut: Konsistente Breiten -->
<div data-md-widget data-mode="object" data-object-id="127" data-width="300"></div>
<div data-md-widget data-mode="object" data-object-id="456" data-width="300"></div>

<!-- ❌ Vermeiden: Zu viele verschiedene Breiten -->
<div data-md-widget data-mode="object" data-object-id="127" data-width="123"></div>
<div data-md-widget data-mode="object" data-object-id="456" data-width="456"></div>
```

## 🆘 Support

### Dokumentation
- Demo-Seite: `demo.html`

### Technische Details
- **API**: museum-digital.org JSON API
- **Framework**: React (intern)
- **Bundler**: Vite
- **Browser-Support**: Moderne Browser (ES2015+)

---

**Viel Erfolg bei der Implementation! 🏛️**
