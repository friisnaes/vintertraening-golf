# Vintertræning Golf 2025/26 🏌️

En simpel hjemmeside hvor alle 8 deltagere kan tilmelde/framelde sig til onsdagstræning.

## Opsætning (følg disse trin)

### Trin 1: Opret Google Sheet

1. Gå til [Google Sheets](https://sheets.google.com)
2. Opret et nyt sheet og kald det **"Vintertræning Golf"**
3. I det første faneblad (sheet), omdøb det til: **Tilmeldinger**
4. I den første række, indsæt disse kolonneoverskrifter:
   - A1: `Dato`
   - B1: `Deltager`
   - C1: `Status`

### Trin 2: Tilføj Google Apps Script

1. I dit Google Sheet, klik på **Extensions** → **Apps Script**
2. Slet al eksisterende kode i editoren
3. Kopiér HELE indholdet fra filen `apps-script.js` og indsæt det
4. Klik **Save** (💾 ikonet)
5. Klik **Deploy** → **New deployment**
6. Klik på tandhjulet ⚙️ ved "Select type" og vælg **Web app**
7. Udfyld:
   - **Description**: "Vintertræning API"
   - **Execute as**: Me
   - **Who has access**: **Anyone** (vigtigt!)
8. Klik **Deploy**
9. Du får nu en **Web app URL** - kopiér denne! Den ser sådan ud:
   ```
   https://script.google.com/macros/s/AKfycby.../exec
   ```

### Trin 3: Konfigurér hjemmesiden

Åbn filen `config.js` i en text editor (TextEdit, Notepad, VS Code, etc.) og find denne linje:

```javascript
appsScriptUrl: 'INDSÆT_DIN_APPS_SCRIPT_URL_HER'
```

Erstat `INDSÆT_DIN_APPS_SCRIPT_URL_HER` med din Web app URL fra Trin 2.

**Eksempel:**
```javascript
// FØR:
appsScriptUrl: 'INDSÆT_DIN_APPS_SCRIPT_URL_HER'

// EFTER:
appsScriptUrl: 'https://script.google.com/macros/s/AKfycby.../exec'
```

Gem filen.

### Trin 4: Upload til GitHub Pages

1. Gå til dit GitHub repository
2. Upload **både** `index.html`, `config.js` og `README.md`
3. Gå til Settings → Pages
4. Vælg branch (main) og mappe (root)
5. Gem og vent et øjeblik
6. Din side vil være tilgængelig på: `https://ditbrugernavn.github.io/repository-navn/`

## Hvordan det virker

- Hver deltager klikker på sit navn ved hver onsdag
- Status skifter: ? → ✓ → ✗ → ? (Ikke svaret → Tilmeldt → Frameldt)
- Alle ser opdateringer automatisk hvert 30. sekund
- Al data gemmes i Google Sheet
- **Ingen API keys eller kompleks opsætning nødvendig!**

## Hvis du får en advarsel første gang

Første gang du besøger siden efter deployment, kan Google vise en sikkerhedsadvarsel:
1. Klik "Advanced"
2. Klik "Go to Vintertræning Golf (unsafe)" 
3. Dette er normalt for self-deployed scripts

## Support

Hvis noget ikke virker:
1. Tjek at Apps Script er deployed som "Web app" med access "Anyone"
2. Tjek at Web app URL er korrekt indsat i vintertræning.html
3. Åbn browser console (F12) for at se eventuelle fejlmeddelelser

## Deltagere

- Jan
- Torben
- Jes
- Kim
- Henrik
- Morten
- Thomas
- Søren
- Mystery guest

**Træning**: Hver onsdag kl. 19:00-20:00  
**Periode**: 19. november 2025 - 1. april 2026  
**Antal træninger**: 19 onsdage

---

## Teknisk information

Denne løsning bruger:
- **GitHub Pages**: Gratis hosting af hjemmesiden
- **Google Sheets**: Database til tilmeldinger
- **Google Apps Script**: Backend API til at læse/skrive data
- **Vanilla JavaScript**: Ingen frameworks, hurtig og simpel
