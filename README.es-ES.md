<div align="center">

# GET SHIT DONE

**Español** · [English](README.md) · [Português](README.pt-BR.md) · [简体中文](README.zh-CN.md) · [日本語](README.ja-JP.md) · [한국어](README.ko-KR.md)

**Un sistema ligero de meta-prompting, ingeniería de contexto y desarrollo guiado por especificaciones para Claude Code, OpenCode, Gemini CLI, Kilo, Codex, Copilot, Cursor, Windsurf y más.**

**Resuelve el context rot — la degradación de calidad que ocurre cuando tu IA llena su ventana de contexto.**

[![npm version](https://img.shields.io/npm/v/get-shit-done-cc?style=for-the-badge&logo=npm&logoColor=white&color=CB3837)](https://www.npmjs.com/package/get-shit-done-cc)
[![npm downloads](https://img.shields.io/npm/dm/get-shit-done-cc?style=for-the-badge&logo=npm&logoColor=white&color=CB3837)](https://www.npmjs.com/package/get-shit-done-cc)
[![Tests](https://img.shields.io/github/actions/workflow/status/gsd-build/get-shit-done/test.yml?branch=main&style=for-the-badge&logo=github&label=Tests)](https://github.com/gsd-build/get-shit-done/actions/workflows/test.yml)
[![Discord](https://img.shields.io/badge/Discord-Join-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/mYgfVNfA2r)
[![X (Twitter)](https://img.shields.io/badge/X-@gsd__foundation-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/gsd_foundation)
[![$GSD Token](https://img.shields.io/badge/$GSD-Dexscreener-1C1C1C?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCIgZmlsbD0iIzAwRkYwMCIvPjwvc3ZnPg==&logoColor=00FF00)](https://dexscreener.com/solana/dwudwjvan7bzkw9zwlbyv6kspdlvhwzrqy6ebk8xzxkv)
[![GitHub stars](https://img.shields.io/github/stars/gsd-build/get-shit-done?style=for-the-badge&logo=github&color=181717)](https://github.com/gsd-build/get-shit-done)
[![License](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)](LICENSE)

<br>

```bash
npx get-shit-done-cc@latest
```

**Funciona en Mac, Windows y Linux.**

<br>

![GSD Install](assets/terminal.svg)

<br>

*"Si sabes claramente lo que quieres, esto LO CONSTRUIRÁ por ti. Sin rodeos."*

*"He probado SpecKit, OpenSpec y Taskmaster — este me ha dado los mejores resultados."*

*"Con diferencia, la adición más potente a mi Claude Code. Nada sobreingeniado. Simplemente hace el trabajo."*

<br>

**Con la confianza de ingenieros de Amazon, Google, Shopify y Webflow.**

</div>

---

> [!IMPORTANT]
> **¿Volviste a GSD?**
>
> Ejecuta `/gsd-map-codebase` para reindexar tu base de código, luego `/gsd-new-project` para reconstruir el contexto de planificación de GSD. Tu código está bien — GSD solo necesita reconstruir su contexto. Consulta el [CHANGELOG](CHANGELOG.md) para ver las novedades.

---

## Por qué lo construí

Soy un desarrollador en solitario. Yo no escribo código — lo escribe Claude Code.

Existen otras herramientas guiadas por especificaciones, pero todas están construidas para organizaciones de ingeniería de 50 personas — ceremonias de sprint, story points, sincronizaciones con stakeholders, flujos de Jira. Yo no soy eso. Soy una persona creativa que intenta construir cosas geniales de manera consistente.

Así que construí GSD. La complejidad está en el sistema, no en tu flujo de trabajo. Por detrás: ingeniería de contexto, formato XML de prompts, orquestación de subagentes, gestión de estado. Lo que ves: unos pocos comandos que simplemente funcionan.

El sistema le da a Claude todo lo que necesita para hacer el trabajo *y* verificarlo. Confío en el flujo. Simplemente hace un buen trabajo.

— **TÂCHES**

---

## Cómo funciona

El bucle son seis comandos. Cada uno hace exactamente una cosa.

### 1. Inicializar

```bash
/gsd-new-project
```

Preguntas → investigación → requisitos → hoja de ruta. Tú lo apruebas y ya estás listo para construir.

> **¿Ya tienes código?** Ejecuta `/gsd-map-codebase` primero. Analiza tu stack, arquitectura y convenciones para que `/gsd-new-project` haga las preguntas correctas.

### 2. Discutir

```bash
/gsd-discuss-phase 1
```

Tu hoja de ruta tiene una frase por fase. Eso no es suficiente para construirlo como *tú* lo imaginas. Discuss captura tus decisiones antes de que se planifique nada: layouts, formas de API, manejo de errores, estructuras de datos — las áreas grises que existen para esta fase específica.

El resultado alimenta directamente la investigación y la planificación. Omítelo y obtendrás valores predeterminados razonables. Úsalo y obtendrás tu visión.

### 3. Planificar

```bash
/gsd-plan-phase 1
```

Investigación → plan → verificación, en bucle hasta que los planes pasen. Cada plan es lo suficientemente pequeño para ejecutarse en una ventana de contexto nueva.

### 4. Ejecutar

```bash
/gsd-execute-phase 1
```

Los planes se ejecutan en oleadas paralelas. Cada ejecutor obtiene un contexto nuevo de 200k tokens. Cada tarea obtiene su propio commit atómico. Ve a hacer otra cosa y regresa a trabajo completado con un historial de git limpio.

Tu ventana de contexto principal se mantiene al 30–40%. El trabajo ocurre en los subagentes.

### 5. Verificar

```bash
/gsd-verify-work 1
```

Revisa lo que se construyó. Todo lo que esté roto obtiene un plan de corrección diagnosticado — listo para re-ejecución inmediata. No depuras manualmente; simplemente vuelves a ejecutar.

### 6. Repetir → Entregar

```bash
/gsd-ship 1
/gsd-complete-milestone
/gsd-new-milestone
```

Repite el ciclo discutir → planificar → ejecutar → verificar → entregar hasta que el milestone esté completo. Luego archiva, etiqueta y comienza el siguiente de nuevo.

---

## Primeros pasos

```bash
npx get-shit-done-cc@latest
```

El instalador te pregunta por tu runtime (Claude Code, OpenCode, Gemini CLI, Kilo, Codex, Copilot, Cursor, Windsurf y más) y si instalar de forma global o local.

```bash
claude --dangerously-skip-permissions
```

GSD está diseñado para automatización sin fricciones. Skip-permissions es la forma en que está pensado para ejecutarse.

Consulta **[docs/USER-GUIDE.md](docs/USER-GUIDE.md)** para el recorrido completo, flags de instalación no interactiva para los 15 runtimes, instalación mínima (`--minimal`), configuración de Docker y configuración de permisos.

---

## Comandos

El bucle principal:

| Comando | Qué hace |
|---------|----------|
| `/gsd-new-project` | Preguntas → investigación → requisitos → hoja de ruta |
| `/gsd-discuss-phase [N]` | Captura decisiones de implementación antes de planificar |
| `/gsd-plan-phase [N]` | Investigación + plan + verificación |
| `/gsd-execute-phase <N>` | Ejecuta planes en oleadas paralelas |
| `/gsd-verify-work [N]` | Pruebas de aceptación manual |
| `/gsd-ship [N]` | Crea un PR del trabajo de la fase verificada |
| `/gsd-progress --next` | Auto-detecta y ejecuta el siguiente paso |
| `/gsd-complete-milestone` | Archiva el milestone y etiqueta el release |
| `/gsd-new-milestone` | Inicia la siguiente versión |

Para tareas ad-hoc, modo autónomo, análisis de base de código, forense y la superficie completa de comandos — consulta **[docs/COMMANDS.md](docs/COMMANDS.md)**.

---

## Por qué funciona

Tres cosas que la mayoría de configuraciones de codificación con IA hacen mal:

**1. Saturación de contexto.** A medida que una sesión crece, la calidad se degrada. GSD mantiene limpio tu contexto principal haciendo el trabajo pesado en contextos de subagentes nuevos. Los investigadores, planificadores y ejecutores comienzan de cero con exactamente lo que necesitan.

**2. Sin memoria compartida.** GSD mantiene artefactos estructurados que sobreviven a los límites de sesión: `PROJECT.md` (visión), `REQUIREMENTS.md` (alcance), `ROADMAP.md` (hacia dónde vas), `STATE.md` (posición actual y decisiones), `CONTEXT.md` (decisiones de implementación por fase). Cada nueva sesión carga estos y sabe exactamente dónde están las cosas.

**3. Sin verificación.** El código que "ejecuta" no es código que "funciona". El paso de verificación de GSD te guía por lo que se construyó, diagnostica fallos con agentes de depuración dedicados y genera planes de corrección antes de que declares una fase como completada.

Consulta **[docs/ARCHITECTURE.md](docs/ARCHITECTURE.md)** para ver en detalle cómo funciona la orquestación multi-agente y la ingeniería de contexto.

---

## Configuración

Los ajustes viven en `.planning/config.json`. Configúralos durante `/gsd-new-project` o actualízalos con `/gsd-settings`.

Parámetros clave:

| Ajuste | Qué controla |
|--------|-------------|
| `mode` | `interactive` (confirma cada paso) o `yolo` (auto-aprueba) |
| Perfiles de modelo | `quality` / `balanced` / `budget` — controla qué modelo usa cada agente |
| `workflow.research` / `plan_check` / `verifier` | Activa/desactiva los agentes de calidad que añaden tokens y tiempo |
| `parallelization.enabled` | Ejecuta planes independientes simultáneamente |

Para la referencia completa de configuración — todos los ajustes, estrategias de branching de git, anulaciones de modelo por runtime, herencia de configuración de workstream, inyección de skills de agente — consulta **[docs/CONFIGURATION.md](docs/CONFIGURATION.md)**.

---

## Documentación

| Doc | Qué contiene |
|-----|-------------|
| [Guía de usuario](docs/USER-GUIDE.md) | Recorrido completo, opciones de instalación, todos los flags de runtime, referencia de configuración |
| [Comandos](docs/COMMANDS.md) | Cada comando con flags y ejemplos |
| [Configuración](docs/CONFIGURATION.md) | Esquema completo de configuración, perfiles de modelo, branching de git |
| [Arquitectura](docs/ARCHITECTURE.md) | Cómo funciona la orquestación multi-agente |
| [Herramientas CLI](docs/CLI-TOOLS.md) | `gsd-sdk query` y seams de dispatch programático del SDK |
| [Características](docs/FEATURES.md) | Índice completo de características |
| [Changelog](CHANGELOG.md) | Qué cambió en cada release |

---

## Solución de problemas

**¿Los comandos no aparecen?** Reinicia tu runtime después de la instalación. GSD se instala en `~/.claude/skills/gsd-*/` (Claude Code), `~/.codex/skills/gsd-*/` (Codex), o el equivalente para tu runtime.

**¿Algo roto?** Vuelve a ejecutar el instalador — es idempotente:
```bash
npx get-shit-done-cc@latest
```

**¿Contenedores o Docker?** Establece `CLAUDE_CONFIG_DIR` antes de instalar para evitar problemas de expansión de tilde:
```bash
CLAUDE_CONFIG_DIR=/home/youruser/.claude npx get-shit-done-cc --global
```

Instrucciones completas de solución de problemas y desinstalación en **[docs/USER-GUIDE.md](docs/USER-GUIDE.md#troubleshooting)**.

---

## Comunidad

| Proyecto | Plataforma |
|---------|----------|
| [gsd-opencode](https://github.com/rokicool/gsd-opencode) | Puerto original de OpenCode |
| [Discord](https://discord.gg/mYgfVNfA2r) | Soporte de la comunidad |

---

## Historial de estrellas

<a href="https://star-history.com/#gsd-build/get-shit-done&Date">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=gsd-build/get-shit-done&type=Date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=gsd-build/get-shit-done&type=Date" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=gsd-build/get-shit-done&type=Date" />
 </picture>
</a>

---

## Licencia

Licencia MIT. Consulta [LICENSE](LICENSE) para más detalles.

---

<div align="center">

**Claude Code es potente. GSD lo hace fiable.**

</div>
