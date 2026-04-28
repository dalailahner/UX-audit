<!-- TODO: -->
<!-- - (mails von michael und lia noch ausformulieren & einarbeiten) -->
<!-- - struktur ordnen -->

## Structure _(ungeordnet)_

Einige Punkte zur Sortierung der Inhalte für die Seite.

### Navigation:

- Medium (touch, mouse, keyboard, screen reader)
- click/touch target sizes (Fitt's Law)
- click paths (3 click rule)
- Suche (Siehe Components/Bereiche)
- Menüs (Siehe Components/Bereiche)

### Werbung:

- intrusive Ads (Lia "UI/UX-mäßig ist es..." & "Auch ist es komisch..."; Michael "große Werbung")
  - layout shift
  - [intrusive ads](https://www.anstrex.com/blog/intrusive-online-advertising-where-do-we-draw-the-ethical-line)
  - [Coalition for Better Ads](https://www.betterads.org/standards/)
- unseriöse Werbung schädigt eigene Seriösität und Qualität. (Michael "click bait Werbung...")
- Ich denke es spricht auch für sich selbst, wenn man als selbstbestimmtes "Qualitätsmedium" mehr und intrusivere Werbung auf seiner Website schaltet als jede virenverseuchte Piraterie-Seite im Netz.

### Visual Consistency:

- gleiche Elemente sehen unterschiedlich aus.
- Keine klare Linie im Design (podcast widget, video thumbnail img, Karriere widget, Artikel carousel btns, pinpoll, Gaue Tabs, ...)
- erzeugt weniger Glaubwürdigkeit und wirkt unseriös. (bin ich auf einer Phishing Seite gelandet? - Effekt)
- sn.at homepage ist mittig, karriere, immo, ... sind linksbündig (Lia mail "Dazu fällt mir immer wieder negativ auf...")
- 3rd Party / SaaS Integrationen (auch teilweise fehlerhaft (Michael "die Pinpoll Umfrage..."))

LÖSUNG:

- Styleguide & design system mit definierten Attributen (Farben, Abstände, Timings, ect.) und Status (standard, hover, disabled, focused, active, ...) erstellen, daran halten & in einer component library ect. zugänglich machen.

### Components/Bereiche:

<!-- TODO NEXT: Lia mail "Login-Maske" -->

- Login (Michael "diverse Login Themen")
  - kein "Login" oder "Registrieren" sondern nur "Anmelden" mit email input und via API call automatisch "Login" oder "Registrieren" anzeigen.
  - verwendung von Password-Managers optimieren (siehe [hier](https://auth0.com/blog/an-accessible-guide-to-wcag-3-3-8-authentication-without-frustration/#:~:text=5.%20Embrace%20password%20managers%20and%20copy%2Dpaste))

- Suche (Lia "Website-Suche:...")
  - info der verwendbaren such-parameter unter der suchmaske bei eingabe (wie zb bei [GitHub](https://blog.logrocket.com/wp-content/uploads/2024/01/Query-syntax-based-search.png))
  - Bei Suche ohne Ergebnisse -> Vorschläge machen welche suchparameter zu ändern sind um Ergebnisse zu bekommen.
  - Link zu "erweiterte Suche" in header Suchleiste.
  - Das Frontend der Suche ist generell ein absoluter Unfall..

- Menü
  - da wurde warum auch immer schon ein Projekt im stressigen Schnellschuss gemacht (wurde natürlich dann sowieso nicht umgesetzt). -> gehört überarbeitet und auch in dieses Projekt mit eingebunden wies ursprünglich geplant war (Link Menü sidebitch).
  - die Auflistung im derzeitigen Menü muss überarbeitet werden. Verschiedene Punkte mit verschiedenen Namen linken zu den gleichen Seiten. Wortwahlen ergeben keinen Sinn. Benennungen sind ungleich der URL zu denen sie führen. Und ich denke mal einige sachen können rausgeschmissen werden und der Rest neu strukturiert werden.
  - Menüpunkte vom "Profil-Menü" mit content dahinter sollen ins "normale" Menü wandern und bleiben sollen nur administrative Punkte (Zahlungen, Profil bearbeiten, Ausloggen, bla bla).
  - Siehe auch Punkt Personalisierung.

- ...

### Personalisierung:

- Startseite soll hauptsächlich mit den Themen gefüllt sein denen der user folgt.
- Ressorts müssen auch "folgbar" sein (idk why tf dies nicht logisch ist).
- light/dark theme
- personalisierbare items im hamburger Menü. Eventuell oberste Zeile im Menü mit "Zuletzt Besucht" mit den zuletzt geklickten Menüpunkten/Themen/ect.
- Einstellung für Anzahl & Themen der push notifications im Profil.
  - tägliche oder wöchentliche Zusammenfassung abonnierter Themen
  - mit Auswahl des Tages & Uhrzeit
  - nicht einfach jeden Tag jede Person mit 20 random notifications zuscheißen.
  - dann kann auch der sinnlose WebPush button von der Seite weg. Niemand will oder braucht den.
- ...

### Performance:

- Die Seite nicht mit 10000 SaaS Produkten zusammenstöpseln. Da spart man sich auch gleich das ganze Geld was der Müll kostet und löst nicht nur performance Probleme. Braucht man halt Developer.
- Klassiker: [Blogartikel "The 49MB Web Page"](https://thatshubham.com/blog/news-audit)
- implement [Signed HTTP Exchanges (SXG)](https://developer.chrome.com/blog/signed-exchanges). (10 part Blog post about SXG starting [here](https://www.pawelpokrywka.com/p/how-i-took-lcp-down-under-350ms))
- Lighthouse, Core Web Vitals & other metrics
- moderne img types (avif anstelle von webp, jpg als fallback)
- Fonts richtig laden
  - fonts nicht im css laden sondern direkt im head prefetchen
  - (blog beitrag aus obsidian hier einfügen)
- ...

### Misc:

- störende Elemente im Textfluss
- help users recognize & recover from errors (error msgs bei formularen)
- interaction design (IxD) (animations & transitions while interacting, status msgs, toasts)
- text
  - text-bg (maybe blur background on text in front of imgs like articles)
  - font-sizes (+ icons & logos)
  - text-spacing (line-height, margins, paddings, letter-spacing)
  - color-contrast
- visual structure ("heute vor..." has scrollbar but no visual container) (gibts des Teil nu?)
- icons verwenden die die richtige bedeutung haben "opens in new tab" icons zb. (Jacobs Law)
- wording/copy überarbeiten.
- CSS für die Druckversion machen. niemand will 200 Seiten Outbrain ausdrucken.
