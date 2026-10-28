# Stile "Covo Arcade"

Stile grafico de **Il Cyber Covo**, ispirato ai giochi arcade/pixel come Balatro.
Ogni nuova schermata, pulsante o effetto deve rispettare queste regole.

## Dove stanno i parametri
- `index.html`, script, blocco **`STYLE`**: titolo e colori delle parole, parametri dello sfondo a vortice.
- `index.html`, CSS, blocco **`STILE "Covo Arcade"`** (in fondo al `<style>`): font, colori, pannelli, pulsanti, CRT.
- `<body class="arcade">`: la classe che attiva lo stile su tutto il gioco.

## Regole
1. **Font**: Pixelify Sans (Google Fonts) ovunque, con ripiego Courier New. Mai `system-ui` o font con grazie.
2. **Contorni scuri**: testi grandi e carte hanno contorno/ombra `#1a1020`.
3. **Pannelli**: fondo `#1d2a33` (leggermente trasparente), bordo spesso 4px `#3a505c`, ombra piena in basso `0 6px 0 #0d1519`, angoli 14px.
4. **Pulsanti a rilievo**: ombra piena sotto `0 5px 0`, premendo scendono di 4px. Angoli 12px, testo 18px.
5. **Colori azione**: rosso `#fe5f55` (Crea tavolo, Fold), blu `#009dff` (Entra), oro/accento del tavolo per le azioni principali.
6. **Schermo CRT**: righe sottili + vignettatura sopra tutto. Intero sulla pagina iniziale, attenuato (`#crt.soft`, opacità .45) al tavolo.
7. **Sfondo a vortice**: shader a pixel grossi, usato nella pagina iniziale e nel tavolo "Vortice".
8. **Foto dei tavoli**: le foto si trasformano in pixel art (blocchi da 5px, 5 livelli per colore, saturazione 1.5) con un velo magenta/azzurro e uno strato scuro per la leggibilità. Parametri in `STYLE.photo`; si attiva con `pixel:true` nel tavolo.
9. **Animazioni delle carte**: distribuzione dal centro (dorso), flop/turn/river che volano e si girano (flop 0,95s a cascata, turn/river 1,1s), carte della mano che si sollevano al tocco. Pause di gioco: 1,9s dopo la distribuzione, 2,3s dopo il flop, 1,8s dopo turn e river.
10. **Azioni**: ogni azione ha un fumetto sopra il giocatore (CHECK, FOLD, CALL, RAISE), check = il riquadro "bussa", fold = le carte volano via, call/raise/all-in = le fiches volano nel piatto. Il piatto si scalda (arancio, poi rosso pulsante) al crescere.
11. **Pagine a fumetto/manga**: da 2 a 6 riquadri inclinati con bordo nero, retino a puntini e sfondo per emozione (preoccupato, arrogante, sorpreso, felice, deluso, disperato, pensieroso). Foto in `faces/<nome>-<emozione>.jpg`. Si attivano su all-in e chiamata all-in sempre; sul rilancio quando il piatto supera il 15%, 35%, 60% delle fiches in gioco (solo se sale di livello o è un rilancio su rilancio); su fold e vittoria con piatto caldo (35%+).
12. **Foto dei giocatori**: nessun filtro, la foto resta normale (ritaglio quadrato 320×320). L'estetica fumetto sta intorno alla foto: riquadri inclinati con bordo nero, raggi e retino ai bordi, alone colorato per emozione, simboli (gocce, scintille, !?), balloon con la battuta e animazioni sulla foto (sorpreso zoom, preoccupato trema, felice rimbalza, deluso si abbassa, pensieroso dondola, arrogante si avvicina, disperato scuote). Ogni emozione è collegata a una situazione di gioco (vedi faces/LEGGIMI.txt).
13. **Zone con bordi**: ogni pagina e ogni area di gioco ha un riquadro con bordo spesso 4px `#3a505c` e linguetta con il nome (TAVOLO, LE TUE CARTE, AZIONI, GIOCATORI, OSPITI E CRONACA). Su smartphone le zone stanno in una colonna; da 900px in su su due colonne (tavolo e carte a sinistra, giocatori a destra) e le carte sono ingrandite del 20% (`--cs`).
14. **Schermata unica da app**: niente scorrimento della pagina, né su PC né su telefono. Barra in alto (Menu, titolo, Esci), pulsante voce fisso in basso, fogli che salgono dal basso su telefono, pulsanti alti almeno 44px, vibrazione sulle azioni. Le zone si ridimensionano da sole (`--cs`) in base all'altezza dello schermo. Installabile sulla schermata Home (manifest e icone).
15. **Carte leggibili**: numero grande in Barlow Condensed ExtraBold con il seme sotto.
16. **Movimento**: titolo che ondeggia, carte che fluttuano; tutto si ferma con "riduci animazioni" del sistema.

## Valori chiave
| Cosa | Valore |
|---|---|
| Titolo | Il `#fff4d6`, Cyber `#3de0ff`, Covo `#ff4fa3` |
| Vortice, colori | magenta `(.86,.16,.52)`, azzurro `(0,.55,.78)`, viola scuro `(.06,.03,.14)` |
| Vortice, parametri | pixel 260, velocità 7, rotazione -0.4, spirale .25, contrasto 3.5, luce .4 |
| Foto in pixel | blocco 5, livelli 5, saturazione 1.5, velo `rgba(255,79,163,.28)` / `rgba(61,224,255,.22)` |
| Dimensioni carte | normali 53×74 px, grandi 90×124 px, piccole 28×39 px |
| Contorno | `#1a1020` |
| Pannello / bordo / ombra | `#1d2a33` / `#3a505c` / `#0d1519` |

## Carte e fiches (cyberpunk)
Predefiniti: carte **Neon Grid**, semi **geometrici** (▲ ● ◆ ■), dorso **Griglia**, fiches **Neon**.
Altri stili: carte Synthwave, Hacker, Chrome, Corpo giallo; dorsi Tramonto, Matrix, Hazard, Chrome; fiches Credito, Synthwave, Chrome, Hacker.
Regola: colori al neon su fondo scuro (o giallo/cromo con testo scuro), bordo colorato con bagliore, quattro colori diversi per i semi.

## Cosa è personalizzabile senza rompere lo stile
Tavoli, stile di carte, semi, dorsi e fiches (blocco `PERSONALIZZAZIONE`): cambiano i colori delle cose di gioco, non le regole qui sopra.
