# Plugin-Datenbank

Produktionsquelle für das Supabase-Plugin-Dashboard.

## Architektur

- `index.html` enthält die komplette statische Web-App.
- Die App liest ausschließlich über den Supabase-RPC `get_plugins_for_web`.
- Der im Frontend verwendete Supabase-Key ist ein Publishable Key; keine Service-Role-Credentials werden im Repository gespeichert.
- Vercel soll dieses Repository per Git-Integration mit dem Produktionsbranch `main` verbinden.
- Jeder Commit auf `main` soll automatisch ein neues Production Deployment erzeugen.

## Betriebsregel für ChatGPT

Änderungen an der Website künftig direkt in diesem Repository vornehmen. Für normale Veröffentlichungen keinen Vercel-MCP-Schreibzugriff verwenden. Nach dem Commit übernimmt die Vercel-Git-Integration das Deployment automatisch.

## Vercel-Ersteinrichtung

In Vercel `Import Git Repository` wählen, `heartmood-glitch/heartmood` auswählen und deployen. Für diese statische Seite sind keine Environment Variables und kein Build Command erforderlich.
