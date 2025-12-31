# LOUBAAN Unit Price Test Checklist

## ✅ Desktop Tests
- [ ] Produktseite mit 5ml/10ml Varianten laden
- [ ] Unit Price wird korrekt angezeigt: "5 ml · X.XXX € / Liter"
- [ ] Klick auf 10ml → Live Update auf neue Unit Price
- [ ] Klick auf 10ml → Savings werden angezeigt: "Du sparst X % (X.XXX € / Liter) gegenüber 5 ml"
- [ ] Klick zurück auf 5ml → Savings verschwinden
- [ ] Preise sind korrekt formatiert (EUR, 3 Dezimalstellen)
- [ ] Mathematik korrekt: (Preis / ml) * 1000 = Preis pro Liter

## ✅ Mobile Tests  
- [ ] Responsive Design funktioniert
- [ ] Touch-Events für Variantenwechsel funktionieren
- [ ] Text ist gut lesbar (nicht zu klein)
- [ ] Buttons sind ausreichend groß für Touch

## ✅ Edge Cases
- [ ] Sold-out Varianten: Unit Price wird trotzdem angezeigt
- [ ] Produkte OHNE ml-Varianten: Nichts wird angezeigt (fail-safe)
- [ ] Produkte mit nur einer Variante: Nur Unit Price, keine Savings
- [ ] Produkte mit unregelmäßigen Option-Namen: Robust handling

## ✅ Performance Tests
- [ ] Variant-Wechsel < 100ms Response Zeit
- [ ] Keine JavaScript-Errors in Console
- [ ] Smooth Animationen (falls aktiviert)
- [ ] Kein Layout-Shift beim Laden

## ✅ Browser Compatibility
- [ ] Chrome/Edge (Desktop + Mobile)
- [ ] Firefox (Desktop + Mobile)  
- [ ] Safari (Desktop + Mobile)
- [ ] Internet Explorer 11 (falls erforderlich)

## ✅ Accessibility Tests
- [ ] Screen Reader kann Unit Price und Savings vorlesen
- [ ] Keyboard-Navigation funktioniert
- [ ] High Contrast Mode unterstützt
- [ ] Reduced Motion respektiert

## ✅ Shopify Integration Tests
- [ ] Cart funktioniert normal (keine Interferenz)
- [ ] Checkout-Prozess unbeeinträchtigt
- [ ] Admin-Backend: Produktpreise korrekt
- [ ] Theme-Updates brechen Funktionalität nicht

## Test-Produkte
1. **Standard-Produkt**: 5ml (€X) und 10ml (€Y) Varianten
2. **Edge-Case**: Produkt ohne ml-Angaben
3. **Single-Variant**: Produkt mit nur einer Größe
4. **Ausverkauft**: Alle Varianten verfügbar vs. eine ausverkauft

## Erwartete Berechnungen
- **5ml bei 49,95€**: 49.950€ / 5ml * 1000 = 9.990€/Liter
- **10ml bei 89,95€**: 89.950€ / 10ml * 1000 = 8.995€/Liter  
- **Savings**: 9.990 - 8.995 = 0.995€/Liter = 10% Ersparnis

## Fehlerbehebung
- **Unit Price erscheint nicht**: Prüfen ob Option1 "X ml" Format hat
- **Savings falsch**: Base Variant Logik prüfen (kleinste ml-Größe)
- **Live Update funktioniert nicht**: Event-Listener für Dawn Theme Variant Events prüfen
- **Styling kaputt**: CSS Konflikt mit bestehenden Dawn Styles