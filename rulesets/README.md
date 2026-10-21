# Rulesets

Rulesets de GitHub que se aplican a los repos de producto de `dupegui-org`. Los aplica la skill `dupegui-base:crear-repo-producto` al crear un repo; también se pueden importar a mano (repo → Settings → Rules → Rulesets → New ruleset → Import a ruleset).

| Archivo | Qué hace |
|---|---|
| `main-protegida.json` | Protege la rama por defecto (`main`): todo cambio entra por PR y se mezcla con squash; bloquea el force push y el borrado de la rama. No exige aprobaciones porque el handbook permite la autorrevisión cuando no hay otra persona. |

En el plan Free, GitHub no permite rulesets en repos privados: la skill avisa y sigue con lo demás. Cuando la organización cambie de plan, un ruleset de organización con estas mismas reglas reemplaza a los rulesets de cada repo.
