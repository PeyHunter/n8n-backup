# n8n Workflow Backup

Dette repository indeholder en automatiseret backup af mine n8n workflows. Som en del af uge 2 i AI-modulet på datamatikerstudiet, har jeg bygget en pipeline, der sikrer, at alt min visuelle kodning bliver gemt i versionsstyring på GitHub.

## Hvordan det virker

Systemet kører automatisk hver dag via en Schedule Trigger i n8n. Workflowet henter alle aktive og inaktive workflows via n8ns interne REST API (/api/v1/workflows) ved brug af en personlig API-nøgle. Dataene bliver derefter formateret med JSON Pretty Print (null, 2) for at sikre læsbarhed og pushet direkte til dette repository via GitHub API'et.

## Workflows i denne backup


- Email Weather Report: Et automatiseret flow, der henter vejrdata fra OpenWeather API og sender en daglig rapport via SMTP.

- Backup Flow: Selve det flow, der administrerer denne backup til GitHub.

## Restore

For at genskabe et workflow, skal JSON-indholdet fra workflows.json kopieres og importeres manuelt i n8n interfacet eller via API'et.
