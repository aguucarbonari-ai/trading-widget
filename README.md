# Trading Widget - OBS Overlays

## obs-text.html - Texto configurable para OBS

Overlay de texto para usar como fuente "Browser" en OBS. Todo se configura desde la URL, sin necesidad de hacer deploy para cambiar el contenido.

### Uso

En OBS, agregar una fuente **Browser** con la URL:

```
https://<tu-usuario>.github.io/trading-widget/obs-text.html?t=Tu texto aquí
```

Para cambiar el texto, simplemente editá la URL en las propiedades de la fuente Browser y refrescá.

### Parámetros

#### Texto

| Parámetro | Alias | Descripción | Valor por defecto |
|-----------|-------|-------------|-------------------|
| `t` | `text` | El texto a mostrar. Usá `\n` para saltos de línea. | `Hello World` |

**Ejemplo:** `?t=EN VIVO` o `?t=Línea 1\nLínea 2`

#### Tipografía

| Parámetro | Alias | Descripción | Valor por defecto |
|-----------|-------|-------------|-------------------|
| `fs` | `fontsize` | Tamaño de la fuente en píxeles. | `48` |
| `ff` | `font` | Familia tipográfica (cualquier font del sistema). | `Arial, sans-serif` |
| `gf` | `googlefont` | Nombre de una Google Font para cargar automáticamente. | - |
| `fw` | `weight` | Grosor de la fuente (`normal`, `bold`, `100`-`900`). | `bold` |

**Ejemplo con Google Font:** `?t=Hola&gf=Montserrat&fs=64`

**Ejemplo con fuente del sistema:** `?t=Hola&ff=Courier New&fw=normal`

#### Colores

| Parámetro | Alias | Descripción | Valor por defecto |
|-----------|-------|-------------|-------------------|
| `c` | `color` | Color del texto en hexadecimal (con o sin `#`). | `#ffffff` (blanco) |
| `bg` | `background` | Color de fondo en hexadecimal, o `transparent`. | `transparent` |

**Ejemplo texto rojo sobre fondo negro:** `?t=ALERTA&c=ff0000&bg=000000`

**Ejemplo fondo transparente (para chroma en OBS):** `?t=Info&c=ffffff&bg=transparent`

#### Efectos de texto

| Parámetro | Alias | Descripción | Valor por defecto |
|-----------|-------|-------------|-------------------|
| `s` | `shadow` | Sombra del texto (formato CSS `text-shadow`). | `2px 2px 4px rgba(0,0,0,0.5)` |
| `o` | `outline` | Color del contorno/borde del texto en hexadecimal. | - (sin contorno) |
| `upper` | - | Flag: convierte el texto a mayúsculas. Solo agregar el parámetro, sin valor. | - |
| `italic` | - | Flag: aplica itálica al texto. Solo agregar el parámetro, sin valor. | - |

**Ejemplo con outline blanco:** `?t=Hola&c=000000&o=ffffff`

**Ejemplo en mayúsculas e itálica:** `?t=breaking news&upper&italic`

#### Espaciado y alineación

| Parámetro | Alias | Descripción | Valor por defecto |
|-----------|-------|-------------|-------------------|
| `a` | `align` | Alineación del texto (`left`, `center`, `right`). | `center` |
| `p` | `padding` | Espaciado interno en píxeles. | `10` |
| `ls` | `spacing` | Espaciado entre letras en píxeles. | - |
| `lh` | `lineheight` | Altura de línea (número o valor CSS, ej: `1.5`). | - |

**Ejemplo con spacing:** `?t=TITULO&ls=5&a=left`

### Ejemplos completos

**Texto simple blanco:**
```
obs-text.html?t=EN VIVO&fs=64&c=ffffff
```

**Título con Google Font y fondo verde chroma:**
```
obs-text.html?t=Próximo tema: Trading&gf=Montserrat&fs=52&c=ffffff&bg=00ff00
```

**Alerta roja con outline:**
```
obs-text.html?t=CONEXIÓN PERDIDA&c=ff0000&fs=72&o=ffffff&upper
```

**Texto multilínea con itálica:**
```
obs-text.html?t=Línea 1\nLínea 2\nLínea 3&fs=36&italic&lh=1.8
```

## ticker-tape.html - Cinta de cotizaciones

Widget de TradingView con cotizaciones en tiempo real (S&P 500, NASDAQ, BTC, ETH, Gold, etc.) para usar como fuente Browser en OBS.

```
https://<tu-usuario>.github.io/trading-widget/ticker-tape.html
```
