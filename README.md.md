# Omen — Private RAG System / Sistema RAG Privado On-Premise

> **IA que nunca olvida. Datos que nunca salen.**  
> *AI that never forgets. Data that never leaves.*

---

## ¿Qué es Omen? / What is Omen?

Omen es un sistema de memoria persistente para modelos de inteligencia artificial, diseñado y construido desde cero para resolver un problema real: **la pérdida de contexto entre sesiones de trabajo con IA.**

A diferencia de las soluciones en la nube, Omen corre **100% offline** en hardware propio. Cero tráfico de red. Cero dependencia de APIs externas. Cero bytes saliendo de tu equipo.

> Omen is a persistent memory system for AI models, built from scratch to solve a real problem: **the loss of context between AI working sessions.**  
> Unlike cloud solutions, Omen runs **100% offline** on your own hardware. Zero network traffic. Zero external API dependency. Zero bytes leaving your machine.

---

## El problema que resuelve / The problem it solves

Cuando trabajas con múltiples modelos de IA en paralelo (ChatGPT, Gemini, modelos locales) aplicando técnicas de triangulación de datos, cada nueva sesión borra el contexto anterior. Reconstruirlo manualmente cuesta horas.

**Omen elimina ese cuello de botella.**

> When working with multiple AI models in parallel using data triangulation techniques, each new session erases the previous context. Rebuilding it manually costs hours.  
> **Omen eliminates that bottleneck.**

---

## Arquitectura / Architecture

Omen está construido sobre **SQLite** con una arquitectura de **10 tablas relacionales** que organizan el conocimiento en capas lógicas:

```
Proyectos → Módulos → Inputs → Conocimiento clasificado
```

### Clasificación epistémica del conocimiento

El sistema clasifica toda la información en tres tipos funcionales:

| Tipo | Descripción | Ejemplo |
|------|-------------|---------|
| **Axioma** | Verdad técnica inmovible | Especificaciones de hardware, protocolos |
| **Evidencia** | Información verificada con fuente | Datos investigados y confirmados |
| **Hipótesis** | Ideas o experimentos temporales | Pruebas en curso, supuestos |

Cada entrada tiene un campo `logic_weight` (0–100) que indica su peso lógico dentro del sistema. Esto permite que el modelo sepa qué información es "ley" y qué es experimento — evitando que se pierda en datos irrelevantes.

---

## Características principales / Key Features

- **Memoria persistente estructurada** — el contexto sobrevive entre sesiones, proyectos y reinicios
- **100% offline / air-gapped** — 0 Kbps de tráfico verificado, soberanía total de datos
- **Pipeline de ingesta automática** — importa PDF, Word, Markdown y archivos ZIM (Wikipedia offline / Kiwix)
- **Limpieza de datos** — función `filter_data_zim` que elimina HTML/CSS y entrega solo contexto legible al modelo
- **Vector store listo** — columna `embedding_vector` preparada para búsqueda semántica sin reentrenar
- **Integración con modelos locales** — compatible con Ollama (Llama, Mistral, Qwen y otros)
- **Clasificación epistémica** — sistema de confianza con Axiomas, Evidencias e Hipótesis

---

## Stack técnico / Tech Stack

| Componente | Tecnología |
|------------|------------|
| Base de datos | SQLite |
| Lenguaje principal | Python |
| Modelos locales | Ollama (Llama 3, Mistral, Qwen) |
| Ingesta de documentos | PDF, DOCX, Markdown, ZIM |
| Búsqueda semántica | Embeddings vectoriales (en integración) |
| Plataforma | Windows / Linux — sin GPU dedicada requerida |

---

## Requisitos mínimos de hardware / Minimum Hardware

Omen fue diseñado para correr en hardware de consumo sin GPU dedicada:

- CPU: AMD Ryzen 7 o equivalente (8 núcleos+)
- RAM: 16 GB mínimo (32 GB recomendado para modelos 13B+)
- Almacenamiento: 50 GB libres mínimo
- GPU dedicada: **no requerida** para modelos hasta 14B cuantizados

---

## Casos de uso / Use Cases

Omen está diseñado para organizaciones e individuos que manejan información sensible:

- **Despachos de abogados** — expedientes y contratos que no pueden salir del entorno local
- **Clínicas y profesionales de salud** — datos de pacientes con cumplimiento HIPAA/privacidad
- **Investigadores y periodistas** — fuentes confidenciales protegidas
- **PYMEs** — conocimiento institucional que no se pierde cuando un empleado se va
- **Desarrolladores** — contexto persistente entre sesiones de trabajo técnico

---

## Estado del proyecto / Project Status

| Componente | Estado |
|------------|--------|
| Arquitectura de base de datos (10 tablas) | ✅ Completo |
| Pipeline de ingesta PDF/DOCX/MD | ✅ Completo |
| Importador ZIM (Wikipedia offline) | ✅ Completo |
| Clasificación epistémica + logic_weight | ✅ Completo |
| Modo 100% offline verificado | ✅ Completo |
| Integración con Ollama (modelos locales) | 🔄 En integración |
| Búsqueda semántica por embeddings | 🔄 En integración |
| Interfaz de usuario | 📋 Roadmap |

---

## Servicios / Services

Ofrezco implementaciones personalizadas de Omen para organizaciones que necesitan:

- IA con memoria persistente sin dependencia de nube
- Cumplimiento de privacidad de datos (GDPR, datos médicos, legales)
- Reducción de costos por tokens de API a escala
- Soberanía total sobre el conocimiento institucional

📩 **Contacto:** [LinkedIn — Alan Mendoza](https://www.linkedin.com/in/alan-mendoza-a46791400)  
📍 **Ubicación:** Hermosillo, Sonora, México

---

## Licencia / License

Este proyecto está protegido bajo **MIT License con Commons Clause**.

Puedes ver el código, aprender de él y usarlo para proyectos personales no comerciales.  
**No está permitido** vender, sublicenciar o usar comercialmente este software sin autorización expresa del autor.

> You may view, learn from, and use this code for personal non-commercial projects.  
> **Selling, sublicensing, or commercial use** is not permitted without explicit authorization from the author.

© 2026 Alan Mendoza — Hermosillo, Sonora, México

---

*Construido con el problema en mente, no con el framework.*  
*Built with the problem in mind, not the framework.*
