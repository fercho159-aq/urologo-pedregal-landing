# Repo: urologoPedregal — Mapa de sedes, dominios y proyectos Vercel

> **IMPORTANTE para Claude:** Antes de editar algo lee este archivo COMPLETO. Las apariencias engañan: nombres de carpetas y dominios NO siempre coinciden con lo que sirven.

---

## Las dos sedes (negocios distintos del mismo cliente)

| Sede | Nombre comercial | Campañas Google Ads |
|---|---|---|
| **Cd. Deportes / Patriotismo** | Centro Urológico de Alta Especialidad (CDMX) | Campaña "urólogo CDMX / Cd. Deportes" |
| **Pedregal** | Clínica de Próstata en Pedregal CDMX | Campaña "urólogo Pedregal / clínica de próstata" |

Son dos landings separadas, con campañas de Ads separadas. **Nunca las mezcles.**

---

## Dominios — a qué sede pertenece cada uno (intención del cliente)

| Dominio | Pertenece a | Debería servir |
|---|---|---|
| `www.cdmxurologo.com` | Cd. Deportes / Patriotismo | Landing de Cd. Deportes |
| `urologospedregal.com` | Pedregal | Landing de Pedregal |

---

## Estado ACTUAL en Vercel (2026-11-17)

> ⚠️ Hay un desalineamiento histórico que el cliente conoce y decidió NO arreglar por ahora. Este repo sirve por error al dominio `cdmxurologo.com`, pero el contenido real del dominio que SÍ se mantiene al día es el de este repo aunque esté bajo el dominio equivocado. No intentar unificar/mover dominios sin permiso explícito.

### Proyecto Vercel `urologo-pedregal-landing` (activo, al día)
- **Repo conectado:** `fercho159-aq/urologo-pedregal-landing` (ESTE repo, `C:\Users\alexi\Desktop\urologoPedregal`)
- **Dominio asignado:** `www.cdmxurologo.com` (+ `urologo-pedregal-landing.vercel.app`)
- **Auto-deploy:** ✅ al pushear a `main` dispara deploy
- **Qué sirve:** contenido de Pedregal (raíz rewriteada a `urologo-pedregal/index.html` vía `vercel.json`)

### Proyecto Vercel `urologo-pedregal-landing-octubre-2026` (viejo, huérfano)
- **Repo conectado:** desconocido / desconectado
- **Dominio asignado:** `urologospedregal.com`
- **Último deploy:** 2026-11-10, commit `9ab2b73`
- **Qué sirve:** contenido de Pedregal, pero versión estancada del 10 nov
- **No se puede editar desde este repo** (no está conectado aquí)

---

## Estructura del repo

```
C:\Users\alexi\Desktop\urologoPedregal\
├── vercel.json               ← rewritea `/` → `/urologo-pedregal/index.html`
├── urologo-pedregal/         ← LANDING DE PEDREGAL (TRACKED)
│   ├── index.html            ← landing principal Pedregal
│   ├── cirugias/index.html   ← subpágina cirugía de próstata
│   └── calculos-renales/index.html  ← subpágina cálculos renales
├── blog/                     ← notas de blog (publicadas por herramienta automática externa)
│
├── index.html                ← ⚠️ UNTRACKED — landing vieja de Cd. Deportes, NO se pushea
├── img/, img-hero-*.jpg      ← ⚠️ UNTRACKED — assets de la landing vieja de Cd. Deportes
├── logo.png, logo.avif       ← ⚠️ UNTRACKED — logos viejos
├── reporte.pdf               ← ⚠️ UNTRACKED
└── favicon.ico, favicon-180.png  ← ⚠️ UNTRACKED (los tracked viven en urologo-pedregal/)
```

### Lo que está untracked NO forma parte del deploy actual
Los archivos `index.html`, `img/`, `logo.*`, etc. en la raíz son residuos de cuando este repo era "dos sedes". Quedaron localmente cuando el commit `92555b6` ("chore: remover archivos de Cd. de los Deportes") borró Cd. Deportes del git. **No pushear sin confirmar con el usuario** — romperían la landing de Pedregal que hoy sirve este repo.

---

## Reglas de edición por lo que te pida el usuario

### "Edita Pedregal" / "landing principal de Pedregal" / "la clínica de próstata"
→ Edita `urologo-pedregal/index.html` en ESTE repo
→ Commit + push → se refleja en **`www.cdmxurologo.com`** (sí, suena raro, es por el desalineamiento histórico)
→ **NO se refleja en `urologospedregal.com`** (ese dominio sirve otro proyecto)

### "Edita cirugías" / "cirugía de próstata"
→ `urologo-pedregal/cirugias/index.html`

### "Edita cálculos renales"
→ `urologo-pedregal/calculos-renales/index.html`

### "Edita Cd. Deportes" / "CDMX" / "Patriotismo" / "la landing del dominio cdmxurologo"
→ ⚠️ **PREGUNTAR AL USUARIO** dónde vive hoy. ESTE repo ya no tiene Cd. Deportes en git. El `index.html` local untracked es una versión vieja de referencia, no el fuente productivo.

### "Edita urologospedregal.com"
→ ⚠️ **PREGUNTAR AL USUARIO** — ese dominio no está conectado a este repo. Está en el proyecto Vercel `urologo-pedregal-landing-octubre-2026`, repo desconocido.

---

## Historial útil

- Commit `aa7c446` — agregó Pedregal al repo (cuando este repo era "las dos sedes").
- Commit `92555b6` — ⚠️ borró archivos de Cd. Deportes del repo, dejó solo Pedregal.
- Commit `433563c` — agregó `vercel.json` para que la raíz sirviera Pedregal.
- Commit `4068d2b` — agregó landing `/calculos-renales/`.
- Commit `9ab2b73` — actualizó gtag a `AW-16973737252` (cuenta Google Ads actual).
- Notas de blog en `blog/` — publicadas automáticamente por herramienta externa; no las tocar.

---

## Verificación después de push

Los cambios en `urologo-pedregal/*` se reflejan en `https://www.cdmxurologo.com/` (NO en `urologospedregal.com`). Vercel típicamente deploya en < 2 minutos. Comando rápido para verificar:

```bash
curl -s "https://www.cdmxurologo.com/?v=$(date +%s)" | grep -A2 "Check Up"
```
