# Studywise API Playground – Research & Plan

*Inspelad från experiment 2026-04-03 (Lilly + Robert)*

## Vad är det?

En interaktiv HTML-sida som visar hur Studywise flödet fungerar:
```
Läxa → API-anrop → Flashcards genereras → Concepta → Recall (SRS) → Statistik
```

Utan riktiga API:er – bara mockad data och pilarna som visar hur allt hänger ihop.

## Redan byggt (2026-04-03)

**Repo:** https://github.com/fam-hulten/studywise-api-playground

### Sida 1: Läxa → Flashcards
- POST /api/v1/homework → VocabularyItems med conceptaId
- Concepta API lookup → Visa flashcards med bild
- Klickbar flashcard (vänd på kortet!)

### Sida 2: Träning → SRS → Statistik
- GET /collections/{id}/due → Hämta due items
- Interaktiv flashcard-träning
- Quality buttons (0-5) → Nästa interval beräknas
- Slutstatistik: accuracy, streak, next due

### Tekniskt
- Fristående HTML (CSS/JS inkluderat)
- Mörk tema (#1a1a2e, #e94560 accent)
- Kan hostas var som helst (GitHub Pages, öppnas lokalt)

## DOMÄN-MODELLER (från API specs)

### Concepta (innehåll)
- **Concept** – språkoberoende entitet (t.ex. "giraff")
- **LexicalEntry** – språkspecifik representation (ord, språk, ordklass)
- **Forms** – böjningar med stabila IDs för SRS
- **Representation** – text, bild, ljud, video ("sticky logic")

### Recall (SRS)
- **Collection** – övning/lista (t.ex. glosförhör)
- **LearnableItem** – neutral behållare för historik
- **SRSItem** – per användare × item × app (state: ease/stability, due, reps)
- **SRSReviewEvent** – telemetri för varje repetition

## ROLL-FÖRDELNING
- **Robert:** Bygger HTML/JS
- **Lilly:** Hämtar content/mock-data, strukturerar information

## NÄSTA STEG (framtida)
1. Lägga till fler exempel (icke-djur-ord)
2. Mocka fler API-anrop (icke bara vocabulary)
3. Visa actual JSON payloads
4. Lägga till Concepta/Recall toggles
5. Responsive design för mobil
