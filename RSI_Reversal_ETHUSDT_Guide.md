# Guía del Sistema RSI Reverso ETHUSDT — Trading 4H

Versión 1.0 | Autor: Axael | @trader.xael | Calama, Chile

---

## Índice

1. [Introducción](#introduccion)
2. [La premisa del sistema](#la-premisa)
3. [Reglas de entrada](#reglas-de-entrada)
4. [Reglas de salida y gestión](#reglas-de-salida)
5. [Gestión de riesgo](#gestión-de-riesgo)
6. [Kill switch](#kill-switch)
7. [Contexto de mercado](#contexto-de-mercado)
8. [Example trade](#example-trade)
9. [Setup del indicador](#setup-del-indicador)
10. [Journal y seguimiento](#journal-y-seguimiento)
11. [Preguntas frecuentes](#preguntas-frecuentes)
12. [Disclaimer](#disclaimer)

---

## Introducción

Este documento describe un sistema de trading para **ETH/USDT en timeframe de 4 horas** basado en el indicador RSI (Relative Strength Index) con enfoque de reversión de tendencia en zonas de sobrecompra/sobreventa.

El sistema no es una caja mágica. Es una **regla con filtros** que reduce la subjetividad. Sigue las reglas, documenta todo, revisa semanalmente y ajusta con datos, no con emociones.

**Qué incluye este producto:**
- Esta guía (el sistema)
- Plantilla de trading journal
- Plantilla de métricas semanales
- Checklist de pre-operación
- Prompt de IA para análisis de mercado
- Indicador TradingView (companion)

---

## La premisa

El RSI es un indicador de momento que mide la fuerza relativa de los precios. En los extremos:
- **RSI ≤ 30** → condiciones de sobreventa (compradores pueden entrar)
- **RSI ≥ 70** → condiciones de sobrecompra (vendedores pueden entrar)

La estrategia RSI Reverso aprovecha que los mercados tienden a mean-revertir (volver a la media) después de extensiones extremas, especialmente si hay volumen confirmando el movimiento y la tendencia a corto plazo está a favor.

**No operamos RSI en el vacío.** Requerimos confirmación de:
1. Volumen (el movimiento tiene respaldo de participantes reales)
2. Tendencia a corto plazo (no operamos contra la estructura)
3. Contexto de mercado (no operamos en noticias volátiles o laterales claros)

---

## Reglas de entrada

### Operación LONG (compra)

Todas las condiciones deben cumplirse en el **cierre de una vela 4H**:

| # | Condición | Detalle |
|---|-----------|---------|
| 1 | RSI(14) cruza por debajo de 30 y empieza a girar hacia arriba | El cierre de la vela muestra RSI subiendo desde zona de sobreventa. El valor exacto puede ser 28, 29, 30, 31 — lo importante es la reversión. |
| 2 | Precio está en o cerca de un soporte reciente | Mínimo 5-10 velas de retroceso desde el último movimiento alcista. El precio no debe estar en una zona de impulso fuerte contra la operación. |
| 3 | Volumen de la vela de señal > 1.5× promedio de 20 velas | El movimiento de reversión debe tener participación real, no es un fake. |
| 4 | No hay noticias macro de alto impacto en las próximas 4h | Revisa fuentes antes de entrar. Una noticia importante puede invalidar la señal. |
| 5 | Tendencia a corto plazo (EMA 9/21 en 4H) es alcista o neutral | No operar LONG si el precio está claramente en tendencia bajista estructural (EMA 9 < EMA 21 y precio bajo ambas). |

### Operación SHORT (venta)

Todas las condiciones deben cumplirse en el **cierre de una vela 4H**:

| # | Condición | Detalle |
|---|-----------|---------|
| 1 | RSI(14) cruza por encima de 70 y empieza a girar hacia abajo | Reversión del sobrecompra. |
| 2 | Precio está en o cerca de una resistencia reciente | El precio no debe estar en zona de breakout fuerte a favor de la operación. |
| 3 | Volumen de la vela de señal > 1.5× promedio de 20 velas |
| 4 | No hay noticias macro de alto impacto en las próximas 4h |
| 5 | Tendencia a corto plazo (EMA 9/21 en 4H) es bajista o neutral |

### Niveles de confianza

| Nivel | Condiciones | Acción |
|-------|-------------|--------|
| 🟢 **Verde (alta confianza)** | RSI extremo + volumen alto + soporte/resistencia clara + tendencia a favor | Operar |
| 🟡 **Amarillo (media confianza)** | RSI extremo + volumen moderado + soporte/resistencia menos claro | Operar con tamaño reducido (50% del normal) |
| 🔴 **Rojo (baja confianza)** | RSI marginal (no extremo) + volumen bajo + sin soporte/resistencia claro + mercado lateral | NO operar |

---

## Reglas de salida y gestión

### Take profit

- **Mínimo R:R 2:1** (take profit al menos el doble del riesgo del stop loss)
- Ejemplo: entrada 2000, stop loss 1960 (40 USDT de riesgo = 2%), take profit mínimo 2080 (80 USDT = 4% = 2:1)
- Para operaciones de alta confianza, considerar R:R 3:1 o más si el contexto lo permite

### Stop loss

- **Stop loss fijo antes de entrar** — nunca operar sin uno definido
- Stop loss basado en la estructura de precio, no solo en un porcentaje arbitrario
- Ejemplo: stop loss por debajo del mínimo de la vela de señal o por debajo del último swing low
- Máximo riesgo por operación: **1-2% del capital total**

### Trailing stop (opcional, avanzado)

Una vez que el precio se mueve a tu favor:
- Mover stop loss a break-even cuando el precio avanza 1R (el riesgo inicial)
- Trailing stop adicional cuando el precio alcanza +2R, +3R, etc.
- Documentar en el journal si y cómo usaste trailing stop

### Gestión during trade

- No mover el stop loss más cerca del precio sin una razón estructural clara
- Documentar cada modificación en el journal
- Una operación bien gestionada puede salir en P&L positivo aunque la señal original no se concretara al 100%

---

## Gestión de riesgo

### Reglas absolutas

| Regla | Límite |
|-------|--------|
| Riesgo por operación | Máximo 2% del capital |
| Drawdown diario máximo | 3% del capital (si se alcanza → parar operaciones del día) |
| Operaciones consecutivas perdidas | Máximo 3 antes de parar y revisar |
| Volatilidad extrema | Si ATR > 3× promedio 30d → reducir tamaño o no operar |
| Mercado lateral | Si ADX < 20 → no operar (el RSI reverso funciona mejor en tendencia) |

### Regla de tamaño de posición

```
tamaño_posición = (capital × riesgo_por_operación) / (precio_entrada - stop_loss)
```

Ejemplo:
- Capital: 1000 USDT
- Riesgo por operación: 2% = 20 USDT
- Entrada: 2000 USDT
- Stop loss: 1960 USDT (40 USDT de distancia)
- Tamaño posición = 20 / 40 = 0.5 ETH = 1000 USDT de exposición

---

## Kill switch

El kill switch es una **regla automática** que detiene las operaciones sin pedir permiso. Diseñado para proteger el capital cuando el sistema no está funcionando o el mercado cambia.

### Condiciones de activación

| Condición | Acción |
|-----------|--------|
| Drawdown del día > 3% del capital | Parar operaciones del día. Revisar mañana. |
| 3+ operaciones consecutivas en pérdida | Parar operaciones. Revisar el sistema y el contexto. |
| ATR > 3× promedio 30d | Reducir tamaño al 50% o no operar. |
| ADX < 20 | No operar (mercado lateral, filtrado). |
| Noticia inesperada de alto impacto | Salir de operaciones abiertas con cautela, no abrir nuevas. |

### Registro del kill switch

En el journal semanal, documentar:
- ¿ Se activó el kill switch? (sí/no)
- Si sí, cuál condición lo activó
- Qué aprendiste de la situación
- Qué ajustar para la próxima vez

---

## Contexto de mercado

El sistema no opera en el vacío. El mercado tiene estados diferentes y el sistema funciona mejor en algunos que en otros.

### Estados del mercado

| Estado | Características | Acción del sistema |
|--------|-----------------|-------------------|
| **Tendencia alcista clara** | Precios haciendo máximos y mínimos altos, EMA 9 > 21, ADX > 25 | Sistema LONG funciona bien. Evitar SHORT. |
| **Tendencia bajista clara** | Mínimos y máximos bajistas, EMA 9 < 21, ADX > 25 | Sistema SHORT funciona bien. Evitar LONG. |
| **Lateral / rango** | Precios moviéndose entre soporte y resistencia sin dirección clara, ADX < 20 | **NO operar**. El RSI reverso genera muchas falsas señales en lateral. |
| **Volatilidad extrema** | ATR muy alto, movimientos bruscos, noticias recientes | Reducir tamaño o no operar. Esperar a que se estabilice. |

### Calendario económico

Antes de cada operación, verificar:
- ¿ Hay noticias de la FED, BCE, o datos macro importantes en las próximas 4h?
- ¿ Hay eventos del mercado de cripto (ETF, regulación, seguridad de exchange)?

Si hay noticias de alto impacto, **no operar** la señal. Esperar al cierre de la vela posterior a la noticia.

---

## Example trade

### Trade LONG ejemplo

**Contexto:**
- Fecha: 15 de julio de 2026
- ETH/USDT 4H
- Precio antes de señal: 2150 USDT
- Tendencia 4H: alcista (EMA 9 > EMA 21)
- Noticias: ninguna importante programada

**Señal de entrada (cierre de vela 4H):**
- RSI(14) cierra en 28.5, abrió en 31 y cierra en 28.5, girando hacia arriba en la vela siguiente
- Volumen de la vela: 2.3× promedio 20 velas
- Precio cerca de soporte reciente (mínimo de la vela anterior a 2100)
- EMA 9 > EMA 21 → tendencia a favor

**Ejecución:**
- Entrada: 2150 USDT (al cierre)
- Stop loss: 2090 USDT (por debajo del soporte, 60 USDT = ~2.8% del capital)
- Take profit: 2270 USDT (120 USDT = 2× el riesgo = R:R 2:1 mínimo)
- Tamaño posición: capital × 2% / 60 = tamaño en ETH

**Desarrollo:**
- Vela siguiente: precio sube a 2180, RSI sube a 35
- Trailing stop: se mueve a break-even (2150) cuando precio alcanza 2210 (+1R)
- El precio luego alcanza 2270, take profit ejecutado
- Resultado: +120 USDT, R:R 2:1, win

**Lecciones:**
- La espera del cierre de vela evitó operar intra-candle cuando el RSI aún no había confirmado la reversión
- El volumen alto dio confianza en la señal
- El trailing stop a break-even protegió la operación

### Trade SHORT ejemplo

Similar al anterior pero en dirección opuesta, con RSI > 70, resistencia reciente, volumen alto, y EMA 9 < EMA 21.

---

## Setup del indicador

### TradingView — Volume Momentum V1 (indicador companion)

El archivo `volume_momentum_v1.pine` incluido en este paquete es un indicador TradingView que implementa parte de la lógica del sistema:

1. Abre TradingView → Pine Editor
2. Copia el contenido del archivo `.pine`
3. Pega en el editor y haz clic en "Add to chart"
4. Configura parámetros en el panel de settings (icono de engranaje)
5. El indicador muestra: RSI de volumen, señales de compra/venta, tabla de información

**Versiones de timeframe recomendadas:**
- Principal: 4H (para el sistema RSI reverso)
- Confirmación: 1H o 15min para entrada más precisa (opcional)

### Configuración por defecto del indicador

| Parámetro | Valor default |
|-----------|---------------|
| RSI período | 14 |
| Sobrecompra (RSI) | 70 |
| Sobreventa (RSI) | 30 |
| EMA rápida | 9 |
| EMA lenta | 21 |
| Período volumen promedio | 20 |
| Multiplicador volumen | 1.5 |
| Cooldown alertas | 3 velas |

---

## Journal y seguimiento

El trading sin registro es como navegar sin brújula. El journal es donde aprendes.

### Qué registrar en cada operación

| Campo | Descripción |
|-------|-------------|
| Fecha/hora | Cierre de la vela de señal (UTC recomendado) |
| Par | ETH/USDT (o otro par si aplica) |
| Dirección | LONG o SHORT |
| RSI al cierre | Valor exacto del RSI |
| Volumen relativo | Ratio volumen / promedio |
| Precio de entrada | Precio real al entrar |
| Stop loss | Precio del stop colocado |
| Take profit | Precio del take profit |
| R:R esperado | Ratio riesgo/beneficio planeado |
| Tamaño de posición | En ETH o USD |
| Riesgo % del capital | % del capital arriesgado |
| Resultado | WIN / LOSS / BREAKEVEN |
| P&L | Ganancia/perdida en USDT |
| R:R real | Ratio real alcanzado |
| Lecciones | Qué funcionó, qué mejorar |
| Confianza antes de entrar | 1-10 |
| Disciplina (cumplimiento del plan) | 1-10 |

### Plantillas incluidas

- `trade_journal_template.md` — template para cada operación (Markdown, compatible con Obsidian/Notion)
- `weekly_metrics_template.md` — template para revisión semanal con métricas y evaluación

### Ritual de journal

1. **Después de cada operación:** registrar en el journal (máx 5 minutos)
2. **Al final de cada semana:** completar la plantilla de métricas semanales
3. **Al final de cada mes:** revisar patrones, win rate por nivel de confianza, drawdowns

---

## Preguntas frecuentes

### ¿ El RSI reverso funciona siempre?
No. Ningún sistema funciona siempre. El RSI reverso tiene períodos de excelente desempeño y períodos de drawdown. La clave es:
- Operar solo cuando el sistema cumple TODAS las condiciones
- Respetar los límites de riesgo
- Documentar y mejorar continuamente

### ¿ Cuánto capital necesito para empezar?
Mínimo recomendado: $100-200 USDT para operar ETH/USDT con tamaños razonables. Con menos capital, el riesgo por operación puede ser muy pequeño en términos absolutos, pero el aprendizaje sigue siendo válido.

### ¿ Puedo usar el sistema en otros pares?
Sí, el sistema puede adaptarse a otros pares, pero requiere:
- Volumen suficiente para que el filtro de volumen funcione
- Comportamiento de precios similar (no todas las criptomonedas tienen el mismo perfil de RSI)
- Empezar con ETH/USDT hasta tener Experiencia y resultados consistentes

### ¿ El indicador TradingView es necesario?
No es necesario, pero ayuda a visualizar las condiciones del sistema de forma rápida. Puedes calcular todo manualmente o con otro software. El indicador es un acompañante, no el sistema en sí.

### ¿ Qué hago si el bot (la versión automatizada) da una señal y yo estoy leyendo esto?
La guía y el bot son complementarios. La guía te da la comprensión; el bot te da la ejecución. Si operas manualmente siguiendo la guía, es válido. Si operas con el bot, revisa el journal igual.

---

## Disclaimer

**Esto no es una recomendación de inversión ni consejo financiero.** El trading de criptomonedas conlleva riesgo significativo de pérdida. Puedes perder todo tu capital.

Pasado desempeño no garantiza resultados futuros. El sistema descrito está basado en experiencia y backtesting, pero los mercados cambian y lo que funcionó puede no funcionar en el futuro.

Operar con responsabilidad:
- Empezar con capital que estés dispuesto a perder
- Respetar estrictamente las reglas de riesgo
- Documentar todo
- Revisar y ajustar basado en datos, no en emociones

**Autor:** Axael | @trader.xael | Calama, Chile
**Contacto:** mathialuke@gmail.com | Telegram: @DREstebot
**Licencia:** Uso personal. Para licencia comercial, contactar al autor.

---

*Guía del Sistema RSI Reverso ETHUSDT — v1.0 | {{DATE}}*
