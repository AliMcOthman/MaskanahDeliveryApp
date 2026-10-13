# 🛵 Maskanah Delivery – Lieferdienst für Maskanah

Eine moderne Webanwendung für Essens- und Lieferbestellungen in **Maskanah, Syrien**. Die Anwendung bietet eine benutzerfreundliche arabische Oberfläche mit RTL-Layout (Rechts-nach-links) und ermöglicht es Kunden, ihre Bestellungen direkt über **WhatsApp** zu übermitteln.

Die Liefergebühren werden automatisch anhand des GPS-Standorts des Kunden und der Entfernung zum Hauptmarkt in Maskanah berechnet.

## ✨ Funktionen

- 🛵 **Modernes, responsives Design:** Arabische RTL-Oberfläche, optimiert für Smartphones, Tablets und Desktop-Computer.
- 💬 **WhatsApp-Bestellung:** Direkte Übermittlung der Bestellung an die autorisierte WhatsApp-Nummer des Lieferdienstes.
- 📍 **Automatische Standortbestimmung:** Ermittlung des Kundenstandorts über die Geolocation-API des Browsers.
- 📏 **Entfernungsberechnung:** Berechnung der Entfernung zum Hauptmarkt in Maskanah mithilfe der Haversine-Formel.
- 💰 **Automatische Liefergebühren:**
  - 150 SYP für die ersten 1.500 Meter.
  - Zusätzlich 5 SYP für jeweils weitere 100 Meter oder einen begonnenen 100-Meter-Abschnitt.
- 🎯 **Standortgenauigkeit:** Überprüfung der GPS-Genauigkeit vor dem Absenden der Bestellung.
- ⚠️ **Fehlerbehandlung:** Verständliche Meldungen bei verweigerter Standortfreigabe, nicht verfügbarer Geolocation oder Zeitüberschreitung.
- 📱 **Progressive Web App (PWA):** Installierbare Webanwendung für Android und iOS mithilfe von `manifest.json` und `sw.js`.
- 🧾 **Übersichtliche WhatsApp-Nachricht:** Enthält ausschließlich die Bestellung, den Google-Maps-Link, die Koordinaten und die Liefergebühr.

## 🚀 Anwendung starten

1. Öffne die Website.
2. Gib deine Bestellung ein.
3. Erlaube den Zugriff auf deinen Standort.
4. Prüfe die berechnete Liefergebühr.
5. Klicke auf **Order Now**, um die Bestellung über WhatsApp zu senden.

Für eine lokale Vorschau kannst du Python verwenden:

```bash
python3 -m http.server 8080
```

Öffne anschließend im Browser:

```text
http://localhost:8080
```

**Hinweis:** Die Geolocation-Funktion und die Installation als PWA benötigen in der Regel eine sichere Verbindung über HTTPS oder eine lokale Entwicklungsumgebung wie `localhost`.

## 📦 Deployment

Das Projekt kann auf verschiedenen Hosting-Plattformen veröffentlicht werden:

- GitHub Pages
- Netlify
- Vercel

Alternativ kann das bereitgestellte Skript verwendet werden:

```bash
./push-to-github.sh
```

## 🧩 Projektstruktur

```text
Maskanah-delivery/
├── index.html          # Hauptseite und PWA-Metadaten
├── manifest.json       # Konfiguration für die App-Installation
├── sw.js               # Service Worker für Offline-Funktionen
├── css/
│   └── styles.css      # Gestaltung und responsives Layout
├── js/
│   └── app.js          # Bestelllogik, Geolocation und WhatsApp
└── icons/              # App-Symbole
```

## ⚙️ Konfiguration

Die wichtigsten Einstellungen befinden sich in `js/app.js`:

| Einstellung | Wert | Beschreibung |
|---|---|---|
| `referencePoint` | `35.967665, 38.030636` | Koordinaten des Hauptmarkts in Maskanah |
| `maxAllowedAccuracy` | `100` Meter | Maximal zulässige GPS-Ungenauigkeit |
| `freeDistanceMeters` | `1500` | Entfernung, die durch die Grundgebühr abgedeckt ist |
| `baseDeliveryFee` | `150` SYP | Grundgebühr für die Lieferung |
| `extraFeePerStep` | `5` SYP | Zusätzliche Gebühr pro 100 Meter |
| `whatsappNumber` | `963983926067` | Autorisierte WhatsApp-Nummer des Lieferdienstes |

## 🛠️ Verwendete Technologien

- HTML5
- CSS3
- JavaScript
- Geolocation API
- WhatsApp-Link-Integration
- Google Maps
- Progressive Web App (PWA)
- Service Worker

## 🎯 Projektziel

Ziel des Projekts ist es, einen einfachen und praktischen Bestellprozess für Kunden in Maskanah bereitzustellen. Durch die automatische Standortbestimmung und die entfernungsabhängige Berechnung der Liefergebühren wird die Bestellung transparenter und komfortabler.

---

© Maskanah Delivery – Schneller und zuverlässiger Lieferservice in Maskanah. 🛵
