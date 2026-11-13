# 🎮 Pac-Tabelline

**Pac-Tabelline** è una rielaborazione in chiave educativa del classico videogioco Pac-Man, progettata per aiutare i bambini della scuola primaria ad allenarsi con le tabelline dall'1 al 10 in modo divertente, dinamico e coinvolgente.

Il gioco è sviluppato in **HTML5, CSS3 e JavaScript (Vanilla)** in un unico file autonomo, senza dipendenze esterne.

---

## 🕹️ Come si Gioca

1. **Seleziona la difficoltà e le tabelline:** Nel menu iniziale è possibile scegliere la difficoltà del gioco (numero di vite e fantasmi) e selezionare su quali tabelline ci si vuole esercitare (da $1$ a $10$).
2. **Trova la risposta corretta:** In alto sullo schermo viene mostrata un'operazione (es. $6 \times 4 = ?$). Nel labirinto compariranno dei pallini dorati contenenti diversi numeri nei cunicoli ciechi: uno è la risposta corretta, gli altri sono distrattori.
3. **Muovi Pac-Man:** Guida Pac-Man verso il numero corretto evitando i fantasmi. 
4. **Super-pillole:** Mangia le pillole più grandi per indebolire temporaneamente i fantasmi ed eventualmente divorarli per guadagnare punti extra.

---

## 🧮 Logica di Estrazione e Pesatura delle Tabelline

Nel contesto delle tabelline da $1$ a $10$ ci sono **$42$ risultati univoci** (prodotti distinti). Tuttavia, la probabilità di estrazione di ciascuna operazione viene gestita in base alla combinazione dei fattori:

### 1. Risultati multipli a pari peso
Molti numeri possono essere generati da diverse combinazioni di fattori. Ad esempio, il valore $24$ si ottiene tramite:
* $6 \times 4$
* $4 \times 6$
* $8 \times 3$
* $3 \times 8$

In questi casi, ciascuna delle combinazioni ha la **stessa probabilità (peso $1.0$)** di essere estratta.

### 2. Sottopeso delle tabelline banali (per $1$ e per $10$)
Alcuni prodotti possono essere ottenuti sia con tabelline standard che con moltiplicazioni "banali" (moltiplicazioni per $1$ o per $10$). 

Prendiamo come esempio il numero $9$:
* $3 \times 3$ (Combinazione standard)
* $1 \times 9$ e $9 \times 1$ (Combinazioni banali)

Per evitare che il gioco risulti troppo semplice proponendo continuamente moltiplicazioni per $1$ o per $10$, il motore di gioco **riduce il peso della combinazione al $50\%$ (peso $0.5$)** se uno dei due fattori è $1$ o $10$. 

In questo modo, operazioni come $3 \times 3$ hanno maggiore probabilità di apparire rispetto a $1 \times 9$.

---

## 🏆 Sistema di Punteggio

Il punteggio del giocatore viene calcolato combinando la precisione sulle tabelline, la velocità di risposta e la raccolta degli elementi nel labirinto:

| Azione | Punteggio | Note |
| :--- | :--- | :--- |
| **Pallino normale** | $+1$ punto | Pillole standard sparse per il labirinto |
| **Super-pillola** | $+10$ punti | Attiva la modalità spavento per i fantasmi ($7$ secondi) |
| **Cattura Fantasma** | $+50$ punti | Mangiando un fantasma quando è vulnerabile |
| **Risposta Corretta** | $+10$ a $+20$ punti | **Formula tempo:** $\max(10, 20 - \lceil\max(0, \text{tempo} - 10)\rceil)$ |

### Dettaglio punteggio tempo
* Rispondere entro **$10$ secondi** garantisce il punteggio massimo di **$20$ punti**.
* Oltre i $10$ secondi, il punteggio degrada di **$1$ punto al secondo** fino ad un minimo garantito di **$10$ punti** per ogni risposta esatta.

---

## ⚙️ Difficoltà Disponibili

| Livello | Vite | Fantasmi | Velocità Fantasmi |
| :--- | :---: | :---: | :--- |
| **Facile** | $10$ | $1$ | Bassa ($3.6$) |
| **Medio** | $5$ | $2$ | Media ($4.2$) |
| **Difficile** | $3$ | $3$ | Alta ($4.8$) |

---

## 🎮 Controlli supportati

* **Tastiera:** Freccette direzionali o tasti `WASD`.
* **Touchscreen:** D-Pad a schermo dinamico (supporta il trascinamento/hold).
* **Gamepad / Joypad:** Supporto nativo via Web Gamepad API.

---

## 🛠️ Requisiti e Installazione

Non è richiesta alcuna installazione o configurazione di server.
1. Scarica il file `index.html`.
2. Apri il file in qualsiasi browser web moderno (Chrome, Firefox, Safari, Edge).