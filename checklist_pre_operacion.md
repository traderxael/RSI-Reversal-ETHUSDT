# Pre-Operation Checklist — RSI Reverso ETHUSDT (4H)

Completa este checklist **antes de cada operación**. Si alguna casilla crítica no se cumple, no operar.

---

## BLOQUE A: Contexto de mercado (debe ser verde para operar)

- [ ] **Mercado no está en lateral claro.** Síntomas de lateral: ADX < 20, precio moviéndose entre soporte y resistencia sin dirección clara, sin volumen sostenido en una dirección. Si lateral → NO OPERAR.
  - Observación: {{MARKET_STATE}} (alcista / bajista / lateral)

- [ ] **Tendencia a corto plazo (4H) identificada.** ¿ La EMA 9 está por encima de la EMA 21 (alcista) o por debajo (bajista)? Si estás oponiéndote a la tendencia estructural, no operas.
  - EMA 9: {{EMA9}} | EMA 21: {{EMA21}} | Tendencia: {{TREND_DIRECTION}}

- [ ] **No hay noticias de alto impacto en las próximas 4h.** Revisa el calendario económico. Si haynoticias importantes programadas → NO OPERAR.
  - Calendario revisado: {{CALENDAR_CHECK}} (sí/no) | Noticias encontradas: {{NEWS_FOUND}}

- [ ] **La volatilidad es manejable.** ATR(14) no está en niveles extremos (no > 3× promedio 30d). Si la volatilidad es extrema, reduce el tamaño o no operas.
  - ATR(14) actual: {{ATR_CURRENT}} | ATR promedio 30d: {{ATR_AVG}} | Ratio: {{ATR_RATIO}}x

---

## BLOQUE B: Señal del RSI (debe cumplir TODAS las condiciones)

**Operación LONG (compra):**
- [ ] RSI(14) en cierre de vela ≤ 30 (zona de sobreventa)
  - RSI actual en cierre: {{RSI_CLOSE}}
- [ ] RSI está girando hacia arriba en la vela siguiente (o la vela de señal cierra con RSI bajando y la vela posterior muestra reversión)
  - RSI dirección: {{RSI_DIRECTION}} (hacia arriba / hacia abajo / sin claro)
- [ ] Precio está en o cerca de un soporte reciente (al menos 5-10 velas de retroceso desde el último movimiento)
  - Soporte identificado en: {{SUPPORT_PRICE}} | Distancia actual al soporte: {{DIST_TO_SUPPORT}}%

**Operación SHORT (venta):**
- [ ] RSI(14) en cierre de vela ≥ 70 (zona de sobrecompra)
  - RSI actual en cierre: {{RSI_CLOSE}}
- [ ] RSI está girando hacia abajo
  - RSI dirección: {{RSI_DIRECTION}}
- [ ] Precio está en o cerca de una resistencia reciente
  - Resistencia identificada en: {{RESISTANCE_PRICE}} | Distancia actual a la resistencia: {{DIST_TO_RESISTANCE}}%

---

## BLOQUE C: Confirmación de volumen

- [ ] Volumen de la vela de señal > 1.5× promedio de 20 velas
  - Volumen actual: {{VOLUME_CURRENT}} | Promedio 20 velas: {{VOLUME_AVG}} | Ratio: {{VOL_RATIO}}x
- [ ] Si no hay volumen suficiente → NO OPERAR (o operar con peso reducido si es amarillo)

---

## BLOQUE D: Estructura de la operación (definir antes de entrar)

**Operación LONG:**
- Entrada planeada: {{ENTRY_PLAN}} USDT
- Stop loss planeado: {{SL_PLAN}} USDT (razón: {{SL_REASON}})
- Take profit planeado: {{TP_PLAN}} USDT (mínimo R:R 2:1)
- R:R esperado: {{RR_PLANNED}} (debe ser ≥ 2:1)
- Tamaño de posición: {{POSITION_SIZE_PLAN}} ETH / {{POSITION_SIZE_USD}} USD
- Riesgo por operación: {{RISK_PLAN}}% del capital (máx 2%)

**Operación SHORT:**
- Entrada planeada: {{ENTRY_PLAN}} USDT
- Stop loss planeado: {{SL_PLAN}} USDT (razón: {{SL_REASON}})
- Take profit planeado: {{TP_PLAN}} USDT (R:R ≥ 2:1)
- R:R esperado: {{RR_PLANNED}}
- Tamaño de posición: {{POSITION_SIZE_PLAN}} ETH / {{POSITION_SIZE_USD}} USD
- Riesgo por operación: {{RISK_PLAN}}% del capital

---

## BLOQUE E: Validación final (QUESTION: ¿ Cumple todo?  )

- [ ] ¿ RSI cumple la condición de sobrecompra/sobreventa? {{RSI_OK}}
- [ ] ¿ Volumen es suficiente? {{VOLUME_OK}}
- [ ] ¿ El mercado tiene tendencia favorable (no lateral)? {{TREND_OK}}
- [ ] ¿ No hay noticias bloqueantes? {{NEWS_OK}}
- [ ] ¿ R:R planeado ≥ 2:1? {{RR_OK}}
- [ ] ¿ Stop loss definido antes de la entrada? {{SL_DEFINED}}
- [ ] ¿ Riesgo por operación ≤ 2% del capital? {{RISK_OK}}
- [ ] ¿ La operación no contradice la estructura de mercado (no operas contra tendencia fuerte)? {{STRUCTURE_OK}}
- [ ] ¿ Confianza en la señal ≥ 6/10? {{CONFIDENCE_SCORE}} (si < 6, reconsiderar)

---

## BLOQUE F: Gestión post-entrada (completar después de operar)

- [ ] ¿ Entrada ejecutada al cierre de vela (no intra-candle)? {{ENTRY_EXECUTED_OK}}
- [ ] ¿ Stop loss colocado en el exchange al entrar? {{SL_PLACED}}
- [ ] ¿ Take profit colocado en el exchange al entrar? {{TP_PLACED}}
- [ ] ¿ Se documentó la operación en el journal? {{JOURNAL_DONE}}

Si la operación se cierra:
- [ ] ¿ Se registró la salida en el journal? {{EXIT_DOCUMENTED}}
- [ ] ¿ Se calculó el P&L real? {{PNL_CALCULATED}}

---

## Decision final

**Antes de operar, responde:**

- ¿ Esta operación cumple TODAS las condiciones del Bloque A, B, C? **{{ALL_CONDITIONS_MET}}**
- ¿ El riesgo es manejable (máx 2% del capital)? **{{RISK_MANAGABLE}}**
- ¿ Estoy tranquilo con esta operación o hay duda/emoción? **{{EMOTIONAL_STATE}}**

Si alguna respuesta es "no" o "no estoy seguro" → **NO OPERAR.** Esperar la próxima señal.

---

**Firma:** {{TRADER_NAME}} | **Fecha/Hora (UTC):** {{DATE_TIME_UTC}} | **Versión del sistema:** v{{VERSION}}

`#RSIReversal` `#trading-checklist` `#ETHUSDT` `#risk-management`
