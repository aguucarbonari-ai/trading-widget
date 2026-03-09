# Trading Widget - OBS Overlays

## obs-text.html - Texto configurable para OBS

Overlay de texto para usar como fuente "Browser" en OBS. Soporta dos modos:

- **Modo estático:** el texto se configura directamente en la URL.
- **Modo Gist (dinámico):** el texto se lee de un GitHub Gist con auto-refresh. Para cambiar el mensaje solo editás el Gist, sin tocar OBS ni hacer redeploy.

### Modo Gist (recomendado para texto dinámico)

#### Setup

1. Crear un Gist en [gist.github.com](https://gist.github.com) con el contenido. Puede ser texto plano o JSON:

   **Texto plano:**
   ```
   EN VIVO - Trading de criptos
   ```

   **JSON (permite usar `\n` para saltos de línea):**
   ```json
   {"text": "Línea 1\nLínea 2"}
   ```

2. Copiar el ID del Gist (la parte final de la URL, ej: `a1b2c3d4e5f6...`)

3. En OBS, agregar una fuente **Browser** con la URL:
   ```
   https://aguucarbonari-ai.github.io/trading-widget/obs-text.html?gist=TU_GIST_ID
   ```

4. Para cambiar el texto: editar el Gist desde el browser o con `gh gist edit GIST_ID`

#### Parámetros del modo Gist

| Parámetro | Descripción | Valor por defecto |
|-----------|-------------|-------------------|
| `gist` | ID del GitHub Gist | - (requerido) |
| `gf_name` | Nombre del archivo dentro del Gist (para gists multi-archivo) | primer archivo |
| `poll` | Intervalo de polling en segundos | `5` |

**Ejemplo con polling cada 10 segundos:**
```
obs-text.html?gist=abc123def456&poll=10&fs=64&c=ffffff
```

### Modo estático (texto en la URL)

En OBS, agregar una fuente **Browser** con la URL:

```
https://aguucarbonari-ai.github.io/trading-widget/obs-text.html?t=Tu texto aquí
```

Para cambiar el texto, editá la URL en las propiedades de la fuente Browser.

### Parámetros de estilo (ambos modos)

#### Texto (solo modo estático)

| Parámetro | Alias | Descripción | Valor por defecto |
|-----------|-------|-------------|-------------------|
| `t` | `text` | El texto a mostrar. Usá `\n` para saltos de línea. | `Hello World` |

#### Tipografía

| Parámetro | Alias | Descripción | Valor por defecto |
|-----------|-------|-------------|-------------------|
| `fs` | `fontsize` | Tamaño de la fuente en píxeles. | `48` |
| `ff` | `font` | Familia tipográfica (cualquier font del sistema). | `Arial, sans-serif` |
| `gf` | `googlefont` | Nombre de una Google Font para cargar automáticamente. | - |
| `fw` | `weight` | Grosor de la fuente (`normal`, `bold`, `100`-`900`). | `bold` |

**Ejemplo con Google Font:** `?gist=ID&gf=Montserrat&fs=64`

#### Colores

| Parámetro | Alias | Descripción | Valor por defecto |
|-----------|-------|-------------|-------------------|
| `c` | `color` | Color del texto en hexadecimal (con o sin `#`). | `#ffffff` (blanco) |
| `bg` | `background` | Color de fondo en hexadecimal, o `transparent`. | `transparent` |

#### Efectos de texto

| Parámetro | Alias | Descripción | Valor por defecto |
|-----------|-------|-------------|-------------------|
| `s` | `shadow` | Sombra del texto (formato CSS `text-shadow`). | `2px 2px 4px rgba(0,0,0,0.5)` |
| `o` | `outline` | Color del contorno/borde del texto en hexadecimal. | - (sin contorno) |
| `upper` | - | Flag: convierte el texto a mayúsculas. | - |
| `italic` | - | Flag: aplica itálica al texto. | - |

#### Espaciado y alineación

| Parámetro | Alias | Descripción | Valor por defecto |
|-----------|-------|-------------|-------------------|
| `a` | `align` | Alineación del texto (`left`, `center`, `right`). | `center` |
| `p` | `padding` | Espaciado interno en píxeles. | `10` |
| `ls` | `spacing` | Espaciado entre letras en píxeles. | - |
| `lh` | `lineheight` | Altura de línea (número o valor CSS, ej: `1.5`). | - |

### Ejemplos completos

**Gist con estilo personalizado:**
```
obs-text.html?gist=abc123&fs=64&c=ffffff&gf=Montserrat&upper
```

**Texto estático simple:**
```
obs-text.html?t=EN VIVO&fs=64&c=ffffff
```

**Alerta roja con outline:**
```
obs-text.html?t=CONEXIÓN PERDIDA&c=ff0000&fs=72&o=ffffff&upper
```

## ticker-tape.html - Cinta de cotizaciones

Widget de TradingView con cotizaciones en tiempo real (S&P 500, NASDAQ, BTC, ETH, Gold, etc.) para usar como fuente Browser en OBS.

```
https://aguucarbonari-ai.github.io/trading-widget/ticker-tape.html
```
