# Definition of Ready y Definition of Done

## Definition of Ready (una historia puede entrar a un sprint si...)
- Tiene criterios de aceptación verificables, escritos en Gherkin.
- Tiene diseño o UX adjunto, o no aplica.
- Sus dependencias están identificadas con "blocked by".
- Está estimada (campo Effort) y cabe en un sprint.
- Fue validada con el cliente o con quien hace de PO.

Las preguntas abiertas que no bloquean el desarrollo no impiden que la historia entre al sprint. Solo las críticas deben estar resueltas antes.

## Definition of Done (una historia está terminada si...)
- El código fue revisado por otra persona y el CI está en verde.
- Cada escenario de aceptación tiene un test automatizado.
- No hay alertas críticas de Dependabot ni secretos expuestos.
- Si hubo una decisión técnica relevante, quedó en un ADR.
- Está desplegado en staging y validado contra los criterios.
- El issue está cerrado y vinculado al PR (`Closes #123`).

## Cambios en una historia
- **Aún no entra a un sprint:** se edita directamente y se anota la fila en "Cambios acordados".
- **Está en desarrollo, cambio pequeño:** se edita, se anota la fila y se avisa a quien la desarrolla.
- **Está en desarrollo, cambio grande:** se termina lo ya hecho y se crea una historia nueva con el cambio.
- **Ya está entregada:** no se reescribe. Se crea una historia nueva que referencia la original ("modifica #34").
- **Cambio de modelo de negocio:** la historia original se cierra como *not planned* con la línea "Reemplazada por #X" al inicio, y se crean historias nuevas.
- Cada cambio indica quién lo aprobó y cómo (correo, reunión).

## Bandeja de entrada (inbox)
- Las ideas, preguntas y propuestas se anotan con la plantilla "Captura rápida", sin clasificarlas.
- Si ya se sabe a qué historia pertenece una pregunta para el cliente, va a la lista de la historia y no al inbox.
- Una vez por semana (en el refinamiento) se procesa todo el inbox, y cada ítem sale por una de cinco vías: pregunta para el cliente, historia o épica, Spike o ADR, mejora de proceso en el handbook, o se cierra como *not planned* con una línea de motivo.
- El inbox debe quedar vacío al terminar.

## Jerarquía de issues
Épica > Feature > Historia de usuario > Tarea o Bug.
GitHub no obliga esta jerarquía: la mantenemos por convención y la revisamos en el refinamiento semanal.

## Flujo de ramas
- `main` siempre desplegable.
- Ramas cortas: `feat/123-descripcion`, `fix/456-descripcion`, `chore/descripcion`.
- Todo cambio entra por PR con al menos una revisión. Nadie hace push directo a `main`.
- Commits con Conventional Commits y merge con squash.
- Producción se despliega solo con un tag `vX.Y.Z`.
