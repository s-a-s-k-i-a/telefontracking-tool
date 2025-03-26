# Telefontracking Tool

Dieses Tool ist eine eigenständige, serverseitige Web-App zur Kategorisierung von eingehenden Telefonanrufen – z. B. über Matelso oder ähnliche Anbieter.\
Entwickelt in PHP mit MySQL-Datenbank, jQuery-Frontend und Google Analytics Integration.

## Features

- Echtzeit-Verarbeitung von Matelso-Anruf-Übermittlungen
- Live-Kategorisierung (Beratung, Einkauf, Reklamation)
- Im Falle der Kategorisierung "Kauf" erscheint ein Kaufdialog für die Eingabe von Bestellsumme und Bestellnummer
- Conversion-Tracking mit Google Analytics (inkl. GCLID)
- Bei Kategorisierung werden Echtzeit Events an Google Analytics gesendet
- SuperAdmin mit Mitarbeiterverwaltung (inkl. Adminrechte & Passwortänderung)
- Automatisches Setup inkl. Tabellenprüfung & SuperUser-Anlage
- Bedienerfreundliche Benutzeroberfläche

## Tech-Stack

- PHP (serverseitig)
- MySQL
- jQuery (AJAX-Handling)
- Google Analytics (Conversion-Tracking)
- Custom CSS (ohne Frameworks)

## Setup

1. Projekt auf Server kopieren
2. `.env`-Datei anlegen:
   ```env
   SUPER_ADMIN_PASSWORD=DeinSuperPasswort
   ```
3. Im Browser `index.php` aufrufen → Das Tool führt automatisch ein Setup durch:
   - Erstellung der Datenbanktabellen `calls` und `staff` (falls nicht vorhanden)
   - Prüfung und Ergänzung fehlender Felder
   - Anlage des Super-Admins (Zugangsdaten siehe `.env`)
4. Einloggen als Super-Admin und erste Mitarbeiterkonten im Interface anlegen
5. Optional: Google Analytics Tracking-ID in das Analytics-Snippet eintragen (Datei: `public/js/analytics_events.js`)

## Sicherheit

- Passwort-Hashing mit `password_hash()`
- Zugriff auf `matelso-push.php` nur mit gültigem API-Key
- Serverseitige Validierung aller Nutzereingaben und Requests
- Keine Inline-Styles oder Scripts – vollständige Trennung von Code, Logik und Darstellung

## Lizenz & Nutzung

Dieses Tool wird unter einer individuellen Lizenz veröffentlicht. Es darf ausschließlich zu nicht-kommerziellen Zwecken verwendet werden. Die kommerzielle Nutzung oder Weitergabe ist nur mit schriftlicher Genehmigung der Entwicklerin gestattet.

➡️ Details siehe [`LICENSE.txt`](LICENSE.txt)

## Entwicklerin

**Saskia Teichmann**  
[https://wp-studio.dev](wp-studio.dev)
Full Stack Web Developer mit Fokus auf WordPress & individuelle PHP-Tools

---

> Dieses Projekt kann auf Anfrage erweitert oder an individuelle Anforderungen angepasst werden.  
> Letzte Aktualisierung: März 2025

---

# Telefontracking Tool (EN)

This tool is a standalone, server-based web application for categorizing incoming phone calls – e.g. from Matelso or similar providers.\
Built with PHP, MySQL, jQuery frontend and Google Analytics integration.

## Features

- Real-time processing of incoming call data (e.g. via webhook)
- Categorization options: Consultation, Purchase, Complaint
- If "Purchase" is selected, a modal allows entry of order number and order value
- Google Analytics conversion tracking (incl. GCLID)
- GA Events are fired on each categorization action
- SuperAdmin user with full staff management (including admin roles & password reset)
- Automatic setup with DB structure check and SuperUser generation
- Simple and user-friendly interface

## Tech Stack

- PHP (server-side)
- MySQL
- jQuery (AJAX-based frontend)
- Google Analytics (event & conversion tracking)
- Custom CSS (no frameworks)

## Setup

1. Copy the project to your web server
2. Create a `.env` file:
   ```env
   SUPER_ADMIN_PASSWORD=YourSuperPassword
   ```
3. Visit `index.php` in the browser → Initial setup runs automatically:
   - Database tables `calls` and `staff` are created if missing
   - Missing fields are automatically added
   - A SuperAdmin is created (credentials via `.env`)
4. Log in as SuperAdmin and create staff members via interface
5. Optional: Add your Google Analytics tracking ID in `public/js/analytics_events.js`

## Security

- Passwords hashed using `password_hash()`
- `matelso-push.php` is protected by an API key
- All input is validated server-side
- Fully separated logic, design, and behavior (no inline code)

## License & Usage

This project is released under a **custom individual license**. Commercial use and redistribution are only allowed with prior written permission from the author.

➡️ See [`LICENSE.txt`](LICENSE.txt) for details.

## Developer

**Saskia Teichmann**  
[https://wp-studio.dev](wp-studio.dev)
Full Stack Web Developer specialized in WordPress & custom PHP tools

---

> Customizations and feature extensions are available on request.
> Last updated: March 2025

