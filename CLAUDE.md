# Repo: urologo-pedregal-landing — SIRVE **Cd. Deportes** (`www.cdmxurologo.com`)

> **ANTES DE EDITAR**: lee esto completo. El nombre del repo confunde: contiene "pedregal" pero NO sirve el dominio de Pedregal. Lo que edites aquí lo verá la campaña CDMX.

---

## Mapa autoritativo (confirmado 2026-11-17)

| Repo GitHub | Local path | Dominio Vercel | Sede |
|---|---|---|---|
| `fercho159-aq/urologo-pedregal-landing` | `C:\Users\alexi\Desktop\urologoPedregal` (ESTE) | `www.cdmxurologo.com` | **Cd. Deportes / Patriotismo** |
| `fercho159-aq/urologo-pedregal-landing-octubre-2026` | `C:\Users\alexi\Desktop\pedregal-real` | `urologospedregal.com` | **Pedregal real** |

---

## Las dos sedes

| Sede | Nombre comercial | Campaña Google Ads |
|---|---|---|
| **Cd. Deportes / Patriotismo** | Centro Urológico de Alta Especialidad (CDMX) | "urólogo CDMX" |
| **Pedregal** | Clínica de Próstata en Pedregal CDMX | "urólogo Pedregal" |

---

## Regla de edición

### El usuario dice "Cd. Deportes", "CDMX", "Patriotismo", "cdmxurologo", "la landing principal"
→ ✅ Editar aquí. El archivo principal es `index.html` (en la raíz).

### El usuario dice "blog" (notas publicadas en cdmxurologo.com/blog)
→ ✅ Editar aquí en `blog/`. Las notas son publicadas por una herramienta automática externa; también se pueden tocar a mano.

### El usuario dice "Pedregal", "clínica de próstata", "urologospedregal.com"
→ ❌ NO editar aquí. Ir a `C:\Users\alexi\Desktop\pedregal-real`.

---

## Estructura del repo (post-rescate 2026-11-17)

```
C:\Users\alexi\Desktop\urologoPedregal\
├── index.html                ← LANDING PRINCIPAL Cd. Deportes (editar esto)
├── logo.png, logo.avif
├── favicon.ico, favicon-180.png
├── img-hero-main.jpg         ← hero principal
├── img-hero-clinic.jpg       ← hero sección clínica
├── img-hero-tech.jpg         ← hero sección tecnología
├── reporte.pdf               ← descargable
├── img/                      ← imágenes secundarias (cirugia, consulta, laboratorio, paciente, próstata, riñón, tecnología, urgencias, vejiga)
├── blog/                     ← 7 notas del blog + sus imágenes + index.html del listado
├── vercel.json               ← rewrites para /cirugias y /calculos-renales (legacy — ver siguiente sección)
└── urologo-pedregal/         ⚠️ SNAPSHOT CONGELADO de Pedregal (NO editar aquí para cambios de Pedregal)
```

### Rewrites y `urologo-pedregal/` — estado legacy

`vercel.json` mantiene:
```json
{ "source": "/cirugias", "destination": "/urologo-pedregal/cirugias/index.html" }
{ "source": "/calculos-renales", "destination": "/urologo-pedregal/calculos-renales/index.html" }
```

Estas rutas existen por si alguna campaña Google Ads CDMX apuntaba a `cdmxurologo.com/cirugias` o `cdmxurologo.com/calculos-renales`. **El contenido real de esas páginas pertenece a Pedregal**, pero se sirven desde aquí para no romper enlaces vivos. Si se confirma que ninguna campaña CDMX los usa, se pueden eliminar esos rewrites y la carpeta `urologo-pedregal/` del repo.

**NUNCA** editar `urologo-pedregal/*.html` aquí pensando que son Pedregal — son un snapshot congelado. El Pedregal real vive en el otro repo.

---

## Historial útil

- Commit `aa7c446` — metieron Pedregal al repo.
- Commit `92555b6` — ⚠️ borraron archivos de Cd. Deportes del git (origen del lío).
- Commit `433563c` — rewritearon `/` a Pedregal (origen del lío).
- Commit `9ab2b73` — gtag a `AW-16973737252`.
- **Commit `89538f9` (2026-11-17)** — RESCATE: restauramos Cd. Deportes a la raíz, quitamos el rewrite de `/`, trackeamos todos los assets necesarios. cdmxurologo.com volvió a ser Cd. Deportes.
- Notas en `blog/` — publicadas por herramienta externa automática; no las tocar salvo pedido explícito.

---

## Pendientes conocidos

- `index.html` referencia 6 thumbnails inexistentes (`blog/img-calculos.jpg`, `img-cancer-prostata.jpg`, `img-checkup.jpg`, `img-ets.jpg`, `img-prevencion-calculos.jpg`, `img-prostata.jpg`) en la sección "Blog" del home. Posiblemente también enlaces a notas no publicadas. Hay que repoblar o quitar esas tarjetas.

---

## Verificación después de push

```bash
curl -s "https://www.cdmxurologo.com/?v=$(date +%s)" | grep -o '<title>[^<]*</title>'
# debe decir "Urólogo en CDMX | Centro Urológico de Alta Especialidad | Cd. de los Deportes"
```
