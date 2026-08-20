# Ecosistema AESBEA — Clube de Benefícios

Este proyecto es **UNA de las dos caras** del mismo producto. NO trabajar aislado.

## Las dos caras (van sincronizadas)

| | Este proyecto | Proyecto hermano |
|---|---|---|
| Qué es | **Landing "Clube de Descontos"** (vitrine pública) | **Sistema de Credencial** (app funcional) |
| URL | aesba-clube-de-descontos.vercel.app | asbea-credencial-6tdl.vercel.app |
| Path | `...\LANDINGS\AESBA---CLUBE-DE-DESCONTOS\` | `...\APPS\propias\asbea-credencial\` |
| Tech | `index.html` estático (array `PARTNERS`) | Next.js + Supabase (panel admin) |
| Cómo se editan los benefícios | A mano en `index.html` | Por el panel admin |

## ⚠️ REGLA DE ORO

**Los parceiros/benefícios de esta landing son LOS MISMOS que van en la carteirinha del sistema.**
Cada vez que se agrega / edita / quita un benefício, hacerlo en **LOS DOS lados**:
1. Acá → editar el array `const PARTNERS = [...]` del `index.html`.
2. En el sistema → cargar el parceiro + benefício por el panel admin.

## Notas técnicas de esta landing

- Cada card: contenedor `aspect-[16/11] overflow-hidden` con `group-hover:scale-110`.
- Los logos necesitan ~28% de margen interno o se cortan en el hover.
- Logos reales en `F:\Meu Drive\--- FREDDY AI PRODUCER STUDIO ---\---LANDINGS---\AESBA\LOGOS\`.
- Deploy: git push a `main` → Vercel automático.

## Mejora futura

Conectar ambos para que la landing lea los benefícios del sistema (sync automático). Hoy es manual.

---

## Pendientes de sync al sistema de credencial

El sistema de credencial (`asbea-credencial`) está pausado desde el **rechazo del orçamento (2026-08-20)** — todo lo que se agrega en la landing queda **pendiente** de cargarse en el panel admin cuando/si el sistema retome. Lista:

| Fecha | Parceiro | Beneficio | Status sistema |
|---|---|---|---|
| 2026-08-20 | Soli Fisioterapia e Pilates | 8% desconto | ⏳ pendiente carga |
| 2026-08-20 | Hotel Faial Prime Suites | Código ASBEASC26 (31/07–20/12/26) | ⏳ pendiente carga |

> Cuando el sistema retome, revisar los objetos `id: '9'` y `id: '10'` en `index.html` y replicarlos en el painel admin (parceiro + benefício + login/senha para el parceiro escanear QRs).
