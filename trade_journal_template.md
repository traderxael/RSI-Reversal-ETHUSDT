# Trading Journal — {{DATE}}

## Operación #{{N}}
- **Fecha:** {{DATE}}
- **Hora (UTC):** {{HOUR_UTC}}
- **Par:** ETH/USDT
- **Dirección:** {{LONG / SHORT}}
- **Timeframe analizado:** 4h
- **Entrada:** {{PRICE}} USDT
- **Stop Loss:** {{SL}} USDT ({{SL_PCT}}% desde entrada)
- **Take Profit:** {{TP}} USDT ({{TP_PCT}}% desde entrada)
- **R:R esperado:** {{RATIO}} ({{R:R_EXPECTED}})
- **Tamaño de posición:** {{POSITION_SIZE}} USD / {{POSITION_SIZE_ETH}} ETH
- **Riesgo por operación:** {{RISK_PCT}}% del capital

---

### Análisis Previo (antes de entrar)

#### Contexto del mercado
- [ ] Tendencia mayor (diario): {{TREND_DIARIO}} (alcista / bajista / lateral)
- [ ] Noticias macro de alto impacto en las próximas 4h: {{NOTICIAS}} (sí/no + detalle)
- [ ] Volatilidad reciente (ATR 14): {{ATR}}

#### Señales del sistema RSI Reverso 4H
- RSI(14) actual: {{RSI_ACTUAL}}
- RSI hace 1 vela: {{RSI_ANTERIOR}}
- ¿RSI cruzó nivel de sobreventa (≤30) o sobrecompra (≥70)? {{RSI_CROSS}}
- ¿RSI gira hacia arriba (compra) o hacia abajo (venta)? {{RSI_DIRECTION}}
- Precio respecto al soporte/resistencia reciente: {{SUPPORT_RESISTANCE}}
- Volumen de la vela de señal vs promedio 20: {{VOL_RATIO}}x

#### Confirmación extra (opcional pero recomendado)
- [ ] Tendencia a corto plazo (EMA 9/21 en 4h): {{EMA_TREND}}
- [ ] Precio en zona de valor (no en extremos): {{PRICE_ZONE}}
- [ ] Patrón de precio (doble fondo, rebote, rompimiento): {{PRICE_PATTERN}}

#### Motivo de entrada (escribe por qué te convence esta operación)
{{ENTRADA_REASON}}

#### ¿Por qué NO entrar? (contra-argumento honesto)
{{CONTRA_ARGUMENT}}

---

### Ejecución

| Paso | Acción | Estado |
|------|--------|--------|
| 1 | Esperar cierre de vela 4h (no operar intra-candle) | [ ] |
| 2 | Validar que RSI cumple condición de entrada | [ ] |
| 3 | Verificar no hay noticias bloqueantes | [ ] |
| 4 | Calcular tamaño de posición (máx 1-2% riesgo) | [ ] |
| 5 | Colocar stop loss antes de entrada | [ ] |
| 6 | Colocar take profit (mínimo R:R 2:1) | [ ] |
| 7 | Registrar entrada en journal | [ ] |

- **Precio real de entrada:** {{REAL_ENTRY}} (diferencia vs plan: {{SLIPPAGE}}%)
- **Stop loss colocado en:** {{SL_PRICE}}
- **Take profit colocado en:** {{TP_PRICE}}
- **Hora de entrada:** {{ENTRY_TIME}}

---

### Gestión During Trade

| Hora (UTC) | Precio | Comentario |
|------------|--------|------------|
| {{TIME_1}} | {{PRICE_1}} | {{NOTE_1}} |
| {{TIME_2}} | {{PRICE_2}} | {{NOTE_2}} |
| {{TIME_3}} | {{PRICE_3}} | {{NOTE_3}} |

- ¿ Entraste en trailing stop? (Sí/No): {{TRAILING}}
- ¿ Stop modificado? (Sí/No / por qué): {{SL_MODIFIED}}
- Emociones durante la operación: {{EMOTIONS}}

---

### Resultado Final

- **Salida:** {{EXIT_PRICE}} USDT
- **Fecha de salida:** {{EXIT_DATE}}
- **Hora de salida:** {{EXIT_TIME}}
- **Método de salida:** {{EXIT_METHOD}} (TP alcanzado / SL alcanzado / manual / trailing)
- **P&L bruto:** {{PNL}} USDT ({{PNL_PCT}}% del capital)
- **Resultado:** {{WIN / LOSS / BREAKEVEN}}
- **R:R real:** {{REAL_RR}} (1.8 / 2.0 / 2.2, etc.)
- **Rentabilidad vs plan:** {{PLAN_VS_REAL}}

---

### Lecciones de esta operación

**Lo que hice bien:**
{{WHAT_WENT_WELL}}

**Lo que mejoraría:**
{{WHAT_TO_IMPROVE}}

**Patrón que se repite (si aplica):**
{{PATTERN}}

**Nivel de confianza en la señal antes de entrar (1-10):**
{{CONFIDENCE}}

**Nivel de cumplimiento del plan (1-10):**
{{DISCIPLINE}}

---

### Screenshot / Evidencia

- Enlace al gráfico: {{CHART_LINK}}
- Descripción de lo que debe verse en el screenshot: {{SCREENSHOT_DESC}}

---

### Notas adicionales

{{EXTRA_NOTES}}

---
*Capturado con el Sistema RSI Reverso ETHUSDT — v{{VERSION}} | Autor: Axael (@trader.xael)*

`#trading` `#ETHUSDT` `#RSIReversal` `#journal`
