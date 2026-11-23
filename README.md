# Scorecard de la Liner · Valcasa

Scorecard diario del Call Center de Valcasa (Tania Rodríguez). Lo que está en
la raíz se publica en GitHub Pages.

La página es un solo archivo estático. Cada 60 segundos pide los datos a un
endpoint de n8n (`ZEBRA | VALCASA | Panel Liner · datos`), que devuelve dos
data tables de n8n. Esas tablas las llena cada hora, de 8 a 21 h (CDMX), el
flujo `ZEBRA | VALCASA | Scorecard Liner · datos dashboard`:

- **Leads recibidos**: Kommo (valcasa.kommo.com), leads creados ese día cuyo
  responsable es o fue primero Tania (7687835). Sin borrados ni fusionados.
- **Llamadas y tiempo de contacto**: CallPicker (`crm.v_lead_contacto_valcasa`).
- **Mensajes**: eventos `outgoing_chat_message` de Kommo creados por Tania.
- **Asignados**: cambios de responsable de Tania a Alexia, Celina, Abraham o
  Luciano (`"Valcasa".kommo_cambios_responsable`).
- **Perdidos**: leads que pasan a Closed - lost en el embudo Liner.
- **Tareas vencidas / sin tareas**: tareas abiertas de Tania en Kommo.

Nada se copia ni se guarda aquí.

## Publicar un cambio

Edita `index.html`, actualiza `version.txt` (y la constante `VERSION` dentro
de `index.html` con el mismo valor) y haz `git push`. Las pestañas abiertas se
recargan solas al detectar la versión nueva.
