# Lead Scoring Automation

Zweites Projekt mit n8n. Ein System, das eingehende Leads automatisch 
bewertet und in eine Tabelle einträgt, je nachdem wie vielversprechend 
sie sind.

## Was das System macht

Ein Formular schickt Name, Firma und Anfrage an einen n8n-Webhook. 
Eine KI (läuft über Groq) bewertet den Lead auf einer Skala von 1-10, 
basierend auf Budget und Dringlichkeit. Ist der Score 7 oder höher, 
gilt der Lead als "Hot" und wird entsprechend markiert - sonst als 
"Normal". Am Ende landet jeder Lead automatisch in einer Google-Sheets-
Tabelle, zusammen mit Score und Begründung.

## Verwendet

- n8n
- Groq API (openai/gpt-oss-120b)
- Google Sheets API

## Zum Ausprobieren

Der Workflow (Lead_Scoring.json) lässt sich in eine eigene n8n-Instanz 
importieren. Braucht dann einen eigenen Groq API-Key und eine eigene 
Google Sheets Verbindung (eigenes Sheet mit den Spalten Name, Firma, 
Score, Grund, Status). test.html zeigt, wie eine Anfrage aussehen muss.

## Was noch nicht so gut ist

- Die Bewertung durch die KI ist nicht immer 100% konsistent bei 
  ähnlichen Anfragen
- Kein Duplikat-Check - der gleiche Lead könnte mehrfach eingetragen werden
- Läuft aktuell nur lokal (localhost)

Nächstes Projekt kommt bald :P
