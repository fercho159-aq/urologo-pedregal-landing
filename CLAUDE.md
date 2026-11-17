# Repo: urologo-pedregal-landing — ESTE REPO ES **Cd. Deportes**, NO Pedregal

> **ANTES DE EDITAR**: lee esto completo. El nombre del repo confunde. Este repo (`fercho159-aq/urologo-pedregal-landing`) sirve al dominio **`www.cdmxurologo.com`** que corresponde a la sede **Cd. Deportes / Patriotismo**, NO a Pedregal.

---

## Mapa autoritativo (confirmado por el cliente 2026-11-17)

| Repo GitHub | Local path | Dominio Vercel | Sede |
|---|---|---|---|
| `fercho159-aq/urologo-pedregal-landing` | `C:\Users\alexi\Desktop\urologoPedregal` (ESTE) | `www.cdmxurologo.com` | **Cd. Deportes / Patriotismo** |
| `fercho159-aq/urologo-pedregal-landing-octubre-2026` | *(otro directorio)* | `urologospedregal.com` | **Pedregal real** |

**Los nombres de los repos están al revés de lo que parece.** El repo con sufijo `-octubre-2026` es el Pedregal real.

---

## Las dos sedes

| Sede | Nombre comercial | Campañas Google Ads |
|---|---|---|
| **Cd. Deportes / Patriotismo** | Centro Urológico de Alta Especialidad (CDMX) | Campaña "urólogo CDMX / Cd. Deportes" |
| **Pedregal** | Clínica de Próstata en Pedregal CDMX | Campaña "urólogo Pedregal / clínica de próstata" |

---

## Regla de edición — leer antes de tocar NADA

### El usuario dice "Pedregal", "clínica de próstata", "cirugía de próstata (Pedregal)", "cálculos renales (Pedregal)", "urologospedregal.com"
→ **NO editar aquí.** Ir al otro repo: `fercho159-aq/urologo-pedregal-landing-octubre-2026`.

### El usuario dice "Cd. Deportes", "CDMX", "Patriotismo", "cdmxurologo.com", o "la landing principal del dominio cdmxurologo"
→ Editar aquí. Pero ⚠️ este repo está en un estado raro (ver sección siguiente): el contenido productivo real de Cd. Deportes está untracked en la raíz y NO se pushea hoy. Antes de editar aquí consultar al cliente.

---

## Estado anómalo de este repo (lo que hay que saber)

Este repo nominalmente es Cd. Deportes pero su contenido en git actualmente sirve Pedregal por error histórico:

- Carpeta `urologo-pedregal/` **tracked** → contenido de Pedregal (metido por error)
- `vercel.json` → rewritea `/` → `/urologo-pedregal/index.html`
- Resultado: `cdmxurologo.com` muestra Pedregal en lugar de Cd. Deportes

La landing original de Cd. Deportes vive **untracked** en la raíz:
- `index.html` (1490 líneas, title "Urólogo en CDMX | Cd. de los Deportes")
- `img/`, `img-hero-*.jpg`, `logo.png`, `logo.avif`, `favicon.ico`, `favicon-180.png`, `reporte.pdf`

**El cliente decidió NO arreglar este desalineamiento por ahora (2026-11-17).** Solo pidió documentarlo.

---

## Historial útil

- Commit `aa7c446` — metieron Pedregal al repo.
- Commit `92555b6` — ⚠️ borraron archivos de Cd. Deportes del git.
- Commit `433563c` — agregaron `vercel.json` para que la raíz sirviera Pedregal.
- Commit `4068d2b` — agregaron landing `/calculos-renales/`.
- Commit `9ab2b73` — gtag a `AW-16973737252`.
- Commit `e25511e` / `2786d70` (2026-11-17) — ⚠️ aplicadas 5 correcciones del doctor (quitar PSA de Check Up Básico $900, quitar "Planes de financiamiento"). **Salieron en cdmxurologo.com en vez de urologospedregal.com** porque este repo no era el correcto. Las mismas correcciones deben replicarse en el repo `-octubre-2026`.
- Notas en `blog/` — publicadas por herramienta automática externa. No tocar.

---

## Verificación después de push

Cambios aquí se reflejan en `https://www.cdmxurologo.com/` (NO en `urologospedregal.com`). Vercel deploya en < 2 min.
