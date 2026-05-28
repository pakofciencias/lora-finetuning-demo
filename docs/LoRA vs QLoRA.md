
```
┌─────────────────────┬──────────────────────┬──────────────────────┐
│                     │       LoRA           │       QLoRA          │
├─────────────────────┼──────────────────────┼──────────────────────┤
│ Modelo base         │ FP16 (congelado)     │ NF4 (cuantizado)     │
│ Parámetros nuevos   │ BA de bajo rango     │ BA de bajo rango     │
│ Precisión entreno   │ FP16/BF16            │ BF16 (solo LoRA)     │
│ VRAM para 1.7B      │ ~5–6 GB              │ ~2–3 GB              │
│ VRAM para 7B        │ ~15–18 GB            │ ~6–8 GB              │
│ Pérdida de calidad  │ Mínima               │ Mínima (demostrado)  │
│ Herramienta         │ PEFT + LoraConfig    │ + BitsAndBytesConfig │
│ Inferencia final    │ Fusionar BA en W     │ Fusionar BA en W     │
└─────────────────────┴──────────────────────┴──────────────────────┘
```

**Punto clave:** en inferencia, ambos producen lo mismo. La diferencia es solo durante el entrenamiento. El adaptador LoRA resultante es idéntico.
