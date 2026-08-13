# Weekly Trading Metrics — {{WEEK_START}} to {{WEEK_END}}

Resumen de desempeño semanal para el sistema RSI Reverso ETHUSDT (4H).

## Métricas Principales

| Métrica | Esta Semana | Semana Anterior | Δ |
|---------|-------------|-----------------|-----|
| Total operaciones | {{TOTAL_TRADES}} | {{LAST_WEEK_TOTAL}} | {{DELTA_TOTAL}} |
| Operaciones ganadoras | {{WINS}} | {{LAST_WEEK_WINS}} | {{DELTA_WINS}} |
| Operaciones perdedoras | {{LOSSES}} | {{LAST_WEEK_LOSSES}} | {{DELTA_LOSSES}} |
| Operaciones sin resultado (abiertas) | {{OPEN}} | {{LAST_WEEK_OPEN}} | {{DELTA_OPEN}} |
| Win rate | {{WIN_RATE}}% | {{LAST_WEEK_WIN_RATE}}% | {{DELTA_WR}} |
| P&L total | {{TOTAL_PNL}} USDT | {{LAST_WEEK_PNL}} USDT | {{DELTA_PNL}} |
| P&L % del capital | {{TOTAL_PNL_PCT}}% | {{LAST_WEEK_PNL_PCT}}% | {{DELTA_PNL_PCT}} |
| R:R promedio (operaciones cerradas) | {{AVG_RR}} | {{LAST_WEEK_AVG_RR}} | {{DELTA_AVG_RR}} |
| Mayor ganancia | {{MAX_WIN}} USDT | {{LAST_WEEK_MAX_WIN}} USDT | {{DELTA_MAX_WIN}} |
| Mayor pérdida | {{MAX_LOSS}} USDT | {{LAST_WEEK_MAX_LOSS}} USDT | {{DELTA_MAX_LOSS}} |
| Operaciones con R:R ≥ 2:1 | {{GOOD_RR_COUNT}} | {{LAST_WEEK_GOOD_RR}} | {{DELTA_GOOD_RR}} |
| Operaciones con stop violado (sin esperar) | {{SL_VIOLATIONS}} | {{LAST_WEEK_SL_VIOLATIONS}} | {{DELTA_SL_VIOLATIONS}} |
| Operaciones intra-candle (entradas prematuras) | {{INTRA_CANDLE}} | {{LAST_WEEK_INTRA}} | {{DELTA_INTRA}} |

---

## Desempeño por Semáforo de Señal

| Color Señal | Total | Ganadas | Perdidas | Win Rate | P&L |
|-------------|-------|---------|----------|----------|-----|
| 🟢 Verde (alta confianza) | {{GREEN_SIGNALS}} | {{GREEN_WINS}} | {{GREEN_LOSSES}} | {{GREEN_WR}}% | {{GREEN_PNL}} USDT |
| 🟡 Amarillo (media confianza) | {{YELLOW_SIGNALS}} | {{YELLOW_WINS}} | {{YELLOW_LOSSES}} | {{YELLOW_WR}}% | {{YELLOW_PNL}} USDT |
| 🔴 Rojo (baja confianza / marginal) | {{RED_SIGNALS}} | {{RED_WINS}} | {{RED_LOSSES}} | {{RED_WR}}% | {{RED_PNL}} USDT |

**Interpretación:** las operaciones verdes deberían tener win rate ≥ 50% y R:R ≥ 2:1 en el largo plazo. Si no, revisa el filtro de confianza.

---

## Desempeño por Día de la Semana

| Día | Operaciones | Ganadas | Perdidas | P&L |
|-----|-------------|---------|----------|-----|
| Lunes | {{MON_TRADES}} | {{MON_WINS}} | {{MON_LOSSES}} | {{MON_PNL}} |
| Martes | {{TUE_TRADES}} | {{TUE_WINS}} | {{TUE_LOSSES}} | {{TUE_PNL}} |
| Miércoles | {{WED_TRADES}} | {{WED_WINS}} | {{WED_LOSSES}} | {{WED_PNL}} |
| Jueves | {{THU_TRADES}} | {{THU_WINS}} | {{THU_LOSSES}} | {{THU_PNL}} |
| Viernes | {{FRI_TRADES}} | {{FRI_WINS}} | {{FRI_LOSSES}} | {{FRI_PNL}} |
| Sábado | {{SAT_TRADES}} | {{SAT_WINS}} | {{SAT_LOSSES}} | {{SAT_PNL}} |
| Domingo | {{SUN_TRADES}} | {{SUN_WINS}} | {{SUN_LOSSES}} | {{SUN_PNL}} |

---

## Drawdown y Gestión de Capital

| Métrica | Valor |
|---------|-------|
| Capital al inicio de la semana | {{START_CAP}} USDT |
| Capital al cierre de la semana | {{END_CAP}} USDT |
| Drawdown máximo de la semana (desde pico) | {{MAX_DD_PCT}}% |
| Drawdown desde último pico de capital | {{CURRENT_DD_PCT}}% |
| ¿ Se activó el kill switch? | {{KILL_SWITCH_ACTIVATED}} |
| Si sí, razón del kill switch | {{KILL_SWITCH_REASON}} |

**Kill switch activado si:**
- Drawdown del día > 3% del capital
- 3+ operaciones consecutivas en pérdida
- Volatilidad (ATR) > 3× promedio 30d
- ADX < 20 (mercado lateral, filtrado)

---

## Evaluación del Sistema Esta Semana

### Señales del sistema detectadas

| Fecha/Hora (UTC) | Tipo | RSI | Precio | Vol Ratio | Resultado |
|------------------|------|-----|--------|-----------|-----------|
| {{SIGNAL_1_DATE}} | {{LONG/SHORT}} | {{RSI_1}} | {{PRICE_1}} | {{VOL_1}}x | {{RESULT_1}} |
| {{SIGNAL_2_DATE}} | {{LONG/SHORT}} | {{RSI_2}} | {{PRICE_2}} | {{VOL_2}}x | {{RESULT_2}} |
| {{SIGNAL_3_DATE}} | {{LONG/SHORT}} | {{RSI_3}} | {{PRICE_3}} | {{VOL_3}}x | {{RESULT_3}} |
| ... (añadir más si hay) | | | | | |

### ¿ El sistema entregó señales esta semana?
{{SIGNALS_DETECTED}} (sí / no)

### ¿ Cuántas señales se operaron?
{{SIGNALS_TRADED}}

### ¿ Cuántas señales se saltaban y por qué?
{{SIGNALS_SKIPPED}} — razones: {{SKIP_REASONS}}

---

## Checklist Semanal de Revisión

### Gestión de riesgo
- [ ] ¿ El riesgo por operación se mantuvo ≤ 2% del capital? {{RISK_OK}}
- [ ] ¿ Alguna operación excedió el riesgo permitido? Si sí, ¿ por qué? {{RISK_EXCEEDED}}
- [ ] ¿ Se respetaron los stops en todas las operaciones? {{SL_RESPECTED}}
- [ ] ¿ El drawdown semanal está dentro de los límites aceptables? {{DD_OK}}

### Ejecución
- [ ] ¿ Todas las entradas fueron al cierre de vela 4H (no intra-candle)? {{CANDLE_DISCIPLINE}}
- [ ] ¿ Se colocó take profit con R:R ≥ 2:1 en todas las operaciones? {{RR_DISCIPLINE}}
- [ ] ¿ Hubo operaciones por impaciencia o por miedo? {{EMOTION_TRADES}}

### Sistema
- [ ] ¿ Las condiciones del mercado favorecieron al sistema esta semana? (tendencia clara vs lateral) {{MARKET_CONDITIONS}}
- [ ] ¿ El filtro de volumen funcionó bien (señales con volumen alto)? {{VOLUME_FILTER_OK}}
- [ ] ¿ Se necesita ajustar algún parámetro del sistema? {{PARAM_ADJUSTMENT_NEEDED}}

### Aprendizaje
- [ ] ¿ Se identificó algún patrón recurrente esta semana? {{PATTERNS_FOUND}}
- [ ] ¿ Qué lección clave saco de esta semana? {{KEY_LEARNING}}

---

## Resumen Ejecutivo

**Semana {{WEEK_NUMBER}} de {{YEAR}} — {{WEEK_START}} a {{WEEK_END}}**

{{EXECUTIVE_SUMMARY}}

**Puntuación semanal (1-10):** {{WEEK_SCORE}}

**Acciones para la próxima semana:**
1. {{ACTION_1}}
2. {{ACTION_2}}
3. {{ACTION_3}}

---

*Generado con el Sistema RSI Reverso ETHUSDT — v{{VERSION}} | Autor: Axael (@trader.xael)*

`#trading` `#ETHUSDT` `#RSIReversal` `#weekly-review`
