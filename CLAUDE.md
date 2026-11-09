# Öredev 2026 – Knowledge Base

Det här är en Obsidian-vault med anteckningar från Öredev 2026, fångade med Pocket. Använd vaulten som kunskapskälla när jag ställer frågor om konferensen.

## Struktur

- `Home.md` – startsida med länkar till alla ämnen och talks per dag.
- `Talks/` – en note per session. **Börja alltid här.** Innehåller frontmatter, sammanfattning, inbäddad mind map och en sektion `My notes`.
- `Topics/` – översiktsnoter (MOC:ar) som grupperar talks per tema.
- `Templates/` – mallar. Använd `Templates/Talk.md` för nya talks.
- `Attachments/` – mind maps och original-PDF:er. Läs eller ändra dem inte.

## Frontmatter

Talk-noter har: `title`, `type`, `event`, `date`, `description`, `tags`, `topics`, `source`, `status`. Filtrera med grep på `tags`, `topics`, `date` och `status` när du söker brett.

## Så svarar du på frågor

- **Svara bara utifrån vaulten.** Om svaret inte finns, säg det tydligt istället för att gissa eller fylla i från allmän kunskap.
- **Ange alltid källa:** vilken talk (som `[[Talknamn]]`) och under vilken rubrik informationen står.
- **Skilj på vad talaren sa och vad du själv drar för slutsats.** Markera tolkningar som dina egna.
- **Notera osäkerhet:** sammanfattningarna är AI-genererade och kan innehålla fel. Flagga när något verkar tveksamt.
- Svara på svenska om jag skriver på svenska. Behåll engelska termer och citat i originalspråk.

## Så skriver du i vaulten

- Skapa nya filer i `Inbox/` om inget annat sägs. Skapa mappen vid behov.
- **Ändra inte befintliga talk-noter eller bilagor** utan att jag ber om det. Undantag: du får fylla i sektionen `My notes` om jag ber dig.
- Använd wikilänkar (`[[Notnamn]]`), inte markdown-länkar, och länka alltid tillbaka till de talks du bygger på.
- Följ frontmatter-mönstret från `Templates/Talk.md`. Tags skrivs i kebab-case, till exempel `developer-experience`.
- Filnamn ska vara läsbara titlar utan specialtecken som `:` eller `/`.
- Visa förslag på större ändringar (nya ämnesnoter, omstruktureringar, många filer) innan du skriver dem.

## Underhåll

- Nya talks läggs i `Talks/` med mallen.
- Lägg till nya talks i rätt `Topics/`-note och i `Home.md`.
- Bilagor namnges `<Titel> - mind map.png` och `<Titel> - summary.pdf`.
