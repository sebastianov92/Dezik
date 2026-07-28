<p align="center">
  <img src="assets/icon.png" width="120" alt="Dezik" />
</p>

<h1 align="center">Dezik</h1>

<p align="center">Fuente de sideload (AltStore / SideStore) para las apps de Dezik.</p>

---

## Añadir la fuente

Copia esta URL en **AltStore** o **SideStore** → *Browse* → *Sources* → **+**:

```
https://raw.githubusercontent.com/sebastianov92/Dezik/main/apps.json
```

## Apps

| App | Bundle ID | Estado |
|-----|-----------|--------|
| Asista | `com.dezik.asista` | placeholder — falta IPA |
| Crona  | `com.dezik.crona`  | placeholder — falta IPA |

## Publicar una app

1. Compila el `.ipa`.
2. Sube el IPA como asset en un **GitHub Release** (tag `asista-1.0.0`, `crona-1.0.0`, …).
3. En `apps.json` de esa versión rellena:
   - `downloadURL` → URL del asset del release.
   - `size` → tamaño del IPA en **bytes** (`stat -f%z App.ipa`).
   - `version`, `date` (YYYY-MM-DD), `minOSVersion`.
4. Sube íconos de app a `apps/<app>/icon.png` y capturas a `screenshotURLs`.
5. Commit + push. AltStore refresca la fuente automáticamente.

## Setup del repo

Reemplaza `sebastianov92` por tu usuario/organización de GitHub en:

- `apps.json` (`iconURL`, `headerURL`, todas las `downloadURL`)
- este `README.md`

```bash
grep -rl sebastianov92 . | xargs sed -i '' 's/sebastianov92/tu-usuario/g'
```

## Estructura

```
Dezik/
├── apps.json          # fuente AltStore Source v2
├── assets/
│   ├── icon.svg       # logo Dezik
│   └── icon.png       # 512×512, usado por AltStore
├── apps/              # íconos/capturas por app
└── README.md
```
