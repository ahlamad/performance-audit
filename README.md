# Performance Audit 

Doe een Performance audit op een bestaande website uit je eigen omgeving en rapporteer daarover.

De instructies van deze opdracht staan in [INSTRUCTIONS](https://github.com/fdnd-task/performance-audit/blob/main/docs/INSTRUCTIONS.md).

De documentatie van deze Performance audit staan in [Wiki](https://github.com/ahlamad/performance-audit/wiki/Performance-audit).

## Merrachi.com

Lighthouse en PageSpeed Insights audit voor desktop en mobiel.

<img width="1612" height="1450" alt="image" src="https://github.com/user-attachments/assets/5a31fa10-ef93-4785-8a43-5f7106e05d2f" />
<img width="1620" height="1392" alt="image" src="https://github.com/user-attachments/assets/23f8b756-b74e-47d5-86d7-9f998d432231" />


## Mobiel

**Lighthouse score: 37**

| Statistiek | Waarde |
|---|---|
| FCP | 3,4 s ❌ |
| LCP | 59,0 s ❌ |
| TBT | 780 ms ❌ |
| CLS | 0 ✅ |

### Problemen
- **Te veel JavaScript** — ongebruikte JS wordt ingeladen op pagina's waar het niet nodig is
- **Zware main-thread** — browser heeft veel CPU-tijd nodig voor HTML, CSS en JS verwerking
- **Afbeeldingen zonder width/height** — reserveert geen ruimte tijdens het laden

### Wat goed gaat
- Geen layout shifts (CLS = 0)
- Snelle server response
- CSS en JS zijn geminimaliseerd
- Viewport correct ingesteld

---

## Desktop

**Lighthouse score: 48**

| Statistiek | Waarde |
|---|---|
| FCP | 0,9 s ✅ |
| LCP | 8,7 s ❌ |
| TBT | 360 ms ❌ |
| CLS | 0 ✅ |

### Problemen
- **JavaScript execution time te hoog** — Google raadt onder de 2 seconden aan
- **Grote payload (~28 MB)** — vooral problematisch op mobiele netwerken
- **Main-thread werk (~3,3s)** — vertraagt interactiviteit

---

## Werkelijkheid vs Lighthouse

De Lighthouse mobiele test simuleert een trage 4G verbinding en een langzame CPU, waardoor de scores veel slechter zijn dan wat echte gebruikers ervaren.

| | Lighthouse | Echte gebruikers (CrUX) |
|---|---|---|
| Mobiel LCP | 59,0 s | 2,0 s ✅ |
| Desktop LCP | 8,7 s | 2,7 s ✅ |

Echte gebruikers hebben betere verbindingen dan de test aanneemt.

<img width="2870" height="1612" alt="image" src="https://github.com/user-attachments/assets/5b65315b-9bd8-45bd-85f0-18548c482a74" />
<img width="2866" height="1620" alt="image" src="https://github.com/user-attachments/assets/2001f73c-6192-40fe-88ec-63985f143ede" />

---

## Bronnen
- [Lighthouse reduce JS execution time](https://developer.chrome.com/docs/lighthouse/performance/bootup-time)
- [Reduce unused JavaScript](https://developer.chrome.com/docs/lighthouse/performance/unused-javascript)
- [Afbeeldingen zonder dimensies](https://web.dev/articles/optimize-cls#images_without_dimensions)

## Licentie

This project is licensed under the terms of the [MIT license](./LICENSE).
