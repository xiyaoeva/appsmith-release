# A2 - Architecture Sketch

## Initial sketch (v1)

Run Query -> Execute API -> Update latest response only

Issue found: no persistent timeline for previous attempts.

## Revised sketch (v2)

Run Query -> Execute API -> Record summary asynchronously -> History tab fetches latest N records

Design decision:
- keep recording async so execution UX is not blocked,
- store only compact preview with redaction and truncation,
- keep strict retention cap per action.
