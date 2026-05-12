# Fine-tuning con LoRA/QLoRA: Instrucción en español

> Proyecto de demostración para el curso *Proyecto I: Introducción a Large Language Models*  
> Facultad de Ciencias, UNAM · Semestre 2026-2

## Descripción

Este proyecto implementa fine-tuning eficiente sobre **Qwen3-1.7B** usando las
técnicas **LoRA** (Hu et al., 2021) y **QLoRA** (Dettmers et al., 2023) para adaptar un modelo base a la tarea de instrucción en español, con énfasis en explicaciones de conceptos de matemáticas aplicadas.

El objetivo es reproducir los conceptos centrales de los papers originales y
documentar cada decisión de diseño, sirviendo como guía para proyectos de titulación.

## Estado del proyecto

🟡 En construcción — Sesión 1: configuración del repositorio

| Fase | Estado |
|------|--------|
| Repositorio y estructura | ✅ En curso |
| Lectura del paper (LoRA/QLoRA) | 🟡 En curso |
| Curación del corpus | ⬜ Pendiente |
| Baseline (modelo sin fine-tuning) | ⬜ Pendiente |
| Fine-tuning con LoRA | ⬜ Pendiente |
| Evaluación | ⬜ Pendiente |
| Deployment (HuggingFace Spaces) | ⬜ Pendiente |

## Papers base

- Hu, E. J., et al. (2021). [LoRA: Low-Rank Adaptation of Large Language Models](https://arxiv.org/abs/2106.09685). ICLR 2022.
- Dettmers, T., et al. (2023). [QLoRA: Efficient Finetuning of Quantized LLMs](https://arxiv.org/abs/2305.14314). NeurIPS 2023.

## Modelo

| Parámetro | Valor |
|-----------|-------|
| Modelo base | `Qwen/Qwen3-1.7B` |
| Técnica | QLoRA 4-bit + LoRA |
| Plataforma de cómputo | Kaggle (GPU T4, free tier) |
| Licencia del modelo | Apache 2.0 |

## Estructura del repositorio

```text
lora-finetuning-demo/
├── notebooks/        # Notebooks por sesión (numerados)
├── data/
│   ├── raw/          # Datos originales sin modificar
│   └── processed/    # Datos listos para entrenamiento
├── models/            # Adaptadores LoRA locales
└── docs/              # Referencias y notas técnicas
```

## Reproducibilidad

Todo el proyecto está diseñado para ejecutarse en **Kaggle free tier** (GPU T4)
sin costo. Las instrucciones completas de reproducción se documentarán en cada notebook.

## Referencia bibliográfica

Si usas este material en tu propio proyecto, cita los papers originales:

```bibtex
@article{hu2021lora,
  title={LoRA: Low-Rank Adaptation of Large Language Models},
  author={Hu, Edward J and Shen, Yelong and Wallis, Phillip and Allen-Zhu, Zeyuan
          and Li, Yuanzhi and Wang, Shean and Wang, Lu and Chen, Weizhu},
  journal={arXiv preprint arXiv:2106.09685},
  year={2021}
}

@article{dettmers2023qlora,
  title={QLoRA: Efficient Finetuning of Quantized LLMs},
  author={Dettmers, Tim and Pagnoni, Artidoro and Holtzman, Ari and Zettlemoyer, Luke},
  journal={arXiv preprint arXiv:2305.14314},
  year={2023}
}
```


