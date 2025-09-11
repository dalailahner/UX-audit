## To Dos:

- (mails von michael und lia noch einarbeiten)
- struktur ordnen

## Structure _(ungeordnet)_:

Einige Punkte zur Sortierung der Inhalte für die Seite.

### Topic

- navigation
  - (touch, mouse, keyboard, screen reader)
  - click paths (3 click rule)
  - menus
  - search
- click/touch target sizes (Fitt's Law)

### Werbung

- intrusive Ads (Lia "UI/UX-mäßig ist es..." & "Auch ist es komisch..."; Michael "große Werbung")
  - layout shift
  - [intrusive ads](https://www.anstrex.com/blog/intrusive-online-advertising-where-do-we-draw-the-ethical-line)
  - [Coalition for Better Ads](https://www.betterads.org/standards/)
- unseriöse Werbung schädigt eigene Seriösität und Qualität. (Michael "click bait Werbung...")

### Visual Consistency

gleiche Elemente sehen unterschiedlich aus. Keine klare Linie im Design.

- consistent styling (podcast widget, video thumbnail img, Karriere widget, Artikel carousel btns, pinpoll, Gaue Tabs, ...)
- dadurch entsteht weniger Glaubwürdigkeit und wirkt unseriös. (bin ich auf einer Phishing Seite gelandet? - Effekt)
- sn.at homepage ist mittig, Unterseite eines Redakteurs, Profil, Suche, Fotoblog, karriere, immo, ... sind linksbündig (Lia mail "Dazu fällt mir immer wieder negativ auf...")
- 3rd Party / SaaS Integrationen (auch teilweise fehlerhaft (Michael "die Pinpoll Umfrage..."))

LÖSUNG:

- Styleguide mit definierten Attributen (Farben, Abstände, Timings, ect.) und Status (standard, hover, disabled, focused, active, ...). Sichtbar in live component library.

### Redesigns

TODO NEXT: Lia mail "Login-Maske"

- Login (Michael "diverse Login Themen")

  - besser strukturieren
  - kein "Login" oder "Registrieren" sondern nur "Anmelden" mit email Feld und via API call automatisch "Login" oder "Registrieren" anzeigen.
  - Passkeys als default verwenden (bzw. passwordless bevorzugen)
  - Passwort nur als letzte möglichkeit wenn die alternativen nicht verfügbar sind oder manuell "mit Passwort einloggen" ausgewählt wird.
    - "Passwort vergessen" direkt zum Passwort input.
  - verwendung von Password-Managers optimieren (siehe [hier](https://auth0.com/blog/an-accessible-guide-to-wcag-3-3-8-authentication-without-frustration/#:~:text=5.%20Embrace%20password%20managers%20and%20copy%2Dpaste))
  - "oder" vor dem Google Login
  - letzte Seite "Herzlich Willkommen" nicht anzeigen weils direkt verschwindet und die buttons dadurch nicht benutzt werden können. (Besser wäre ein kurz erscheinender tooltip beim Profil-Icon)

- Suche (Lia "Website-Suche:...")

  - info der verwendbaren such-parameter unter der suchmaske bei eingabe (wie bei [GitHub](https://blog.logrocket.com/wp-content/uploads/2024/01/Query-syntax-based-search.png))
  - Bei Suche ohne Ergebnisse -> Vorschläge machen welche suchparameter zu ändern um Ergebnisse zu bekommen
  - link zu "erweiterte Suche" (eigene Seite mit Filtern ect.)
  - zeitstrahl weg und generell eine "Filter" section über den Suchergebnissen machen

### Personalisierung

- user kann aussuchten welche Themen im home feed hauptsächlich erscheinen
- Lesezeichen (auch dementsprechend anbieten, mit overlay bei hover bei Artikeln, ect.)
- light/dark theme
- personalisierbare items im hamburger Menü && oberste Zeile im Menü mit "Letzte" mit den zuletzt geklickten Menüpunkten.
- Einstellung für Anzahl & Themen der notifications (tägliche oder wöchentliche Zusammenfassung abonnierter Themen (mit Auswahl des Tages & Uhrzeit) und nicht einfach mit 20 random notifications zuscheißen)
- ...

### TOPIC

- störende Elemente im Textfluss
- help users recognize & recover from errors (error msgs bei formularen)
- text
  - text-bg (maybe blur background on text in front of imgs like articles)
  - font-sizes (+ icons & logos)
  - text-spacing (line-height, margins, paddings, letter-spacing)
  - color-contrast
- visual structure ("heute vor..." has scrollbar but no visual container)
- icons verwenden die die richtige bedeutung haben "opens in new tab" icons zb. (Jacobs Law)
- img sizes (hidpi displays, Artikel 2/3 Kästchen breit, podcast img test, ...)
- interaction feedback (animations & transitions while interacting, status msgs, toasts)

### Performance

- implement [Signed HTTP Exchanges (SXG)](https://developer.chrome.com/blog/signed-exchanges) with [nginx-sxg-module](https://github.com/google/nginx-sxg-module). (10 part Blog post about SXG starting [here](https://www.pawelpokrywka.com/p/how-i-took-lcp-down-under-350ms))
- Lighthouse & other metrics
- Fonts richtig laden
  - man braucht kein "latin" wenn bereits "latin-ext" geladen wird (und auch sicher gebraucht wird)
  - fonts nicht im css laden sondern direkt im head prefetchen
  - (blog beitrag aus obsidian einfügen)

### Redundantes

- WebPush button WEG
- accessability button (bzw. ganzes tool) WEG
- Abonnenten Werbung auszuspielen ist das Allerletzte. Hilft auch kein "das ist nicht das Produkt", "Gibt eh PUR Abo" oder "bei X oder Y ists auch so". Wobei, wer so Argumente bringt sowieso sein gesamtes Weltbild hinterfragen soll und bitte zum Wohle der Menschheit den Zwang unterdrücken mögen wenn sie den Mund aufmachen möchten.
- Druckversion von "Artikel drucken" ist absolut fucked. Lösung: Bei Klick CSS nachladen (@layer druck), damit nicht bei jedem Seitenaufruf das "Druck" CSS geladen wird.
