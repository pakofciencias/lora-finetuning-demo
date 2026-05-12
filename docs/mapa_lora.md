```
┌─────────────────────────────────────────────────────────────┐
│                    PROBLEMA                                  │
│  Fine-tuning completo: costo O(d×k) por capa por tarea      │
└──────────────────────────┬──────────────────────────────────┘
                           │
                    HIPÓTESIS CLAVE
                           │
                    ΔW tiene rango bajo
                           │
        ┌──────────────────┴──────────────────┐
        │                                     │
  FUNDAMENTO MATEMÁTICO               VENTAJA PRÁCTICA
  ΔW ≈ BA                             Sin latencia en inferencia
  B ∈ ℝ^{d×r}, A ∈ ℝ^{r×k}          W' = W₀ + BA (fusionable)
  r ≪ min(d,k)                        
        │
  CONEXIÓN CON SVD
  Truncated SVD: M ≈ Uᵣ Σᵣ Vᵣᵀ
  LoRA: aprende B, A directamente
        │
  HIPERPARÁMETROS
  r: rango (típico: 4, 8, 16, 64)
  α: escala (típico: r o 2r)
  target_modules: qué capas adaptar
        │
  EN CÓDIGO (Sesión 7)
  LoraConfig(r=8, lora_alpha=16,
    target_modules=["q_proj","v_proj"])
```
**Una sola pregunta de verificación para el grupo:**

> "Si tienen un modelo con d = k = 2048 y usan r = 8, ¿cuántos parámetros entrenan con LoRA en esa capa? ¿Cuántos ahorran respecto a fine-tuning completo?"

```
Respuesta:
LoRA:          8 × (2048 + 2048) = 32,768
Completo:      2048 × 2048 = 4,194,304
Ahorro: 4,194,304 / 32,768 ≈ 128×
```