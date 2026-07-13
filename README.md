# Patrik Jordan — Interaktivt CV

En självständig, byggd webbsida (React, förkompilerad — inget byggsteg krävs på GitHub) redo för GitHub Pages.

## Så publicerar du (byt ut din befintliga sida)

1. Lägg `index.html`, `bundle.js`, `styles.css` **och mappen `assets/`** (innehåller ditt porträtt och nedladdningsbara CV:t i PDF) i roten av ditt GitHub Pages-repo (t.ex. `dittnamn.github.io`, eller en undermapp om du använder Project Pages).
2. Committa och pusha.
3. Klart — sidan fungerar direkt utan build-steg eftersom `bundle.js` redan är kompilerad.

Om du använder Project Pages (`dittnamn.github.io/cv`), lägg filerna i en mapp `docs/` eller `cv/` och peka GitHub Pages-inställningen dit under repots **Settings → Pages**.

## Om du vill redigera innehållet själv senare

`cv-source.zip` innehåller källkoden (`App.jsx`, `main.jsx`, `styles.css`) med all text och data samlad i en enda datastruktur högst upp i `App.jsx` — enkelt att uppdatera roller, kompetenser eller siffror.

För att bygga om efter ändringar (kräver Node.js och paketen `react`, `react-dom`, samt `esbuild`):

```bash
npx esbuild main.jsx --bundle --minify --outfile=bundle.js --loader:.jsx=jsx --jsx=automatic
```

Kopiera sedan den nya `bundle.js` och `styles.css` till ditt repo.

## Vad sidan innehåller

- **Hero** med en animerad identitetsgraf som räknar upp till 38 000 hanterade identiteter över 7 bolag — en direkt visualisering av IAM-arbetet på Axfood.
- **Kärnkompetenser** som en klickbar flikvy (Strategi/AI, Säkerhet/Identitet, Styrning/Ledarskap).
- **Erfarenhet** som en expanderbar tidslinje — Axfood-rollen är öppen som standard, övriga roller expanderas med ett klick.
- **Nedladdningsbart CV** som PDF — knapp i hero-sektionen och en kompakt länk i navigationsfältet. Filen ligger i `assets/Patrik_Jordan_CV.pdf` och matchar sidans innehåll ord för ord.
- **Karriärhistorik & certifieringar** i botten.

Sidan är responsiv, respekterar `prefers-reduced-motion`, och har synligt tangentbordsfokus på alla interaktiva element.
