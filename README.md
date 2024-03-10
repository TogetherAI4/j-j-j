[Einfach. PDFToChat](https://www.pdftochat.com/)
  ![PDFToChat – Chat with your PDFs in seconds.](./public/og-image.png)
  # PDFToChat

  Chat mit deinen PDFs in Sekunden. Betrieben von Together AI und Pinecone.

  [Tech Stack](#tech-stack) ·
  [Eigenes deployen](#deploy-your-own) ·
  [Häufige Fehler](#common-errors)
  ·
  [Credits](#credits)
  ·
  [Zukünftige Aufgaben](#future-tasks)
<br/>

## Tech Stack

- Next.js [App Router](https://nextjs.org/docs/app) für das Framework
- Mixtral durch [Together AI](https://dub.sh/together-ai) Inference für den LLM
- M2 Bert 80M durch [Together AI](https://dub.sh/together-ai) für Einbettungen
- [LangChain.js](https://js.langchain.com/docs/get_started/introduction/) für den RAG-Code
- [Pinecone](https://www.pinecone.io/) für die Vektordatenbank
- [Bytescale](https://www.bytescale.com/) für die PDF-Speicherung
- [Vercel](https://vercel.com/) für das Hosting und für die postgres-Datenbank
- [Clerk](https://clerk.dev/) für die Benutzerauthentifizierung
- [Tailwind CSS](https://tailwindcss.com/) für das Styling

## Eigenes deployen

Du kannst diese Vorlage auf Vercel oder einem anderen Host bereitstellen. Beachte, dass du Folgendes benötigst:

- [Together.ai](https://dub.sh/together-ai/) einrichten
- [Pinecone](https://www.pinecone.io/) mit 768 Dimensionen einrichten
- [Bytescale](https://www.bytescale.com/) einrichten
- [Clerk](https://clerk.dev/) einrichten
- [Vercel](https://vercel.com/) einrichten
- (Optional) [LangSmith](https://smith.langchain.com/) für Tracing einrichten.

Siehe die .example.env für eine Liste aller benötigten Umgebungsvariablen.

Du musst auch dein Datenbankschema vorbereiten, indem du `npx prisma db push` ausführst.

## Häufige Fehler

- Überprüfe, ob du eine `.env`-Datei erstellt hast, die deine gültigen (und funktionierenden) API-Schlüssel, Umgebung und Indexnamen enthält.
- Überprüfe, ob du die Vektordimensionen auf `768` gesetzt hast und ob der `Index` mit dem von dir angegebenen Feld in der `.env`-Variablen übereinstimmt.
- Überprüfe, ob du eine Kreditkarte bei Together AI hinterlegt hast, wenn du auf Rate-Limit-Probleme aufgrund der kostenlosen Version stößt

## Credits

- [Youssef](https://twitter.com/YoussefUiUx) für das Design der App
- [Mayo](https://twitter.com/mayowaoshin) für das ursprüngliche RAG-Repo und die Inspiration
- [Jacob](https://twitter.com/Hacubu) für die Hilfe bei LangChain
- Together AI, Bytescale, Pinecone und Clerk für die Unterstützung

## Zukünftige Aufgaben

Hier sind einige zukünftige Aufgaben, die ich geplant habe. Beiträge sind willkommen!

- [ ] Füge ein Papierkorb-Symbol hinzu, damit Benutzer PDFs vom Dashboard löschen und die Löschfunktion implementieren können
- [ ] Probiere verschiedene Einbettungsmodelle wie UAE-large-v1 aus, um zu sehen, ob sich die Genauigkeit verbessert
- [ ] Erforsche bewährte Praktiken für das automatische Scrollen basierend auf anderen Chat-Apps wie ChatGPT
- [ ] Führe etwas Prompt-Engineering für Mixtral durch, um Antworten so gut wie möglich zu gestalten
- [ ] Schütze API-Routen, indem du sicherstellst, dass Benutzer angemeldet sind, bevor Chats ausgeführt werden
- [ ] Führe einen ersten Benchmark durch, um zu überprüfen, wie genau das Chunking / die Rückgewinnung sind
- [ ] Erforsche bewährte Praktiken für das Chunking und die Rückgewinnung und spiele damit herum – idealerweise führe Benchmarks durch
- [ ] Probiere Langsmith aus, um mehr Einblick in die Funktionsweise der RAG-App zu erhalten
- [ ] Füge ein Demo-Video auf der Homepage hinzu, um die Funktionalität einfacher zu demonstrieren
- [ ] Upgrade auf Next.js 14 und behebe etwaige Probleme damit
- [ ] Implementiere Quellen wie Perplexität, um sie anklickbar mit mehr Infos zu machen
- [ ] Füge Analysen hinzu, um die Anzahl der Chats & Fehler zu verfolgen
- [ ] Führe einige Änderungen am Standard-Tailwind `prose` durch, um den Abstand zu verringern
- [ ] Füge eine erste Nachricht mit Beispielfragen hinzu oder füge sie einfach als Blasen auf der Seite hinzu
- [ ] Füge eine Option hinzu, um Antworten als Markdown oder in regulären Absätzen zu erhalten
- [ ] Implementiere etwas Ähnliches wie SWR, um Daten automatisch neu zu validieren
- [ ] Speichere Chats für jeden Benutzer, um später darauf zurückzugreifen, in der Postgres-Datenbank
- [ ] Gib eine Nachricht aus, um Benutzer zu bitten, PDFs zu komprimieren, wenn sie über 10 MB liegen
- [ ] Verwende einen selbstentworfenen benutzerdefinierten Uploader
- [ ] Verwende ein Sitzungs-Tracking-Tool, um besser zu verstehen, wie Benutzer die Website nutzen
- [ ] Füge insgesamt eine bessere Fehlerbehandlung mit entsprechenden Toasts hinzu, wenn Aktionen fehlschlagen
- [ ] Füge Unterstützung für Bilder in PDFs mit etwas wie [Nougat](https://replicate.com/meta/nougat) hinzu

