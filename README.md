# OpenAesthetic v1.1

**OpenAesthetic** is an unofficial source recovery and research project focused on **Aesthetic Client v1.1** for **Minecraft 26.2 Fabric**.

The project aims to document, analyze, and preserve the client's internal architecture and functionality through reverse engineering. It provides a reconstructed Java source tree, class mappings, and technical references to support further research.

> **Disclaimer:** OpenAesthetic is not the original development source code, nor is it an official release or independently rewritten implementation of Aesthetic Client.

## Project Overview

OpenAesthetic provides a structured representation of the recovered client, covering its primary components:

- **Modules:** Combat, movement, rendering, player, and utility functionality.
- **Client Framework:** Module management, settings, events, and user interface components.
- **Minecraft Integration:** Fabric entry points, mixins, and supporting resources.
- **Reverse Engineering:** Class mappings, native method references, and recovered bytecode.

### Recovery Details

| Component | Details |
|---|---|
| Target | Aesthetic Client v1.1 |
| Minecraft Version | 26.2 |
| Mod Loader | Fabric |
| Java Files | 1,631 |
| Indexed Modules | 93 |
| Native Declarations | 2,497 |
| Recovery Method | Static analysis and reverse engineering |

The recovered source includes recognizable modules such as **Anchor Aura** and **Crystal Aura**, alongside other client functionality.

Not all components have been fully reconstructed. Certain classes and methods retain obfuscated identifiers, while some implementations are available only as bytecode or native assembly references.

## Repository Structure

- `src/client/java` — Reconstructed Java source tree.
- `src/main/resources` — Fabric metadata and client assets.
- `src/client/resources` — Client-specific resources and mixin configurations.
- `mappings/modules.tsv` — Index of identified modules.
- `mappings/classes.tsv` — Readable class names and their corresponding JVM identifiers.
- `reference/native/methods.tsv` — Native method declarations and associated code offsets.

These resources are intended to facilitate code inspection, behavioral analysis, and architectural research.

## Building

**Requirements:**
- JDK 25
- Python 3.11 or newer
- Gradle Wrapper (included)

To assemble the recovered JAR:

```powershell
.\gradlew.bat build
```

The resulting artifact is generated at:

`build/libs/Aesthetic.jar`

**Important:** The build process reconstructs the JAR using recovered class files and resources. Modifying the decompiled Java source does not automatically modify the resulting artifact.

### Portable Runtime

The recovered client depends on additional runtime components, including Orbit libraries and the Bizuro JVM environment.

To stage the client using an existing compatible portable installation:

```powershell
.\gradlew.bat stagePortable '-PportableRoot=C:/path/to/Aesthetic-Portable'
```

Launch using:

`build/portable/Start.cmd`

The reconstructed JAR has been compared against all **2,232 entries** of the reference artifact and smoke-tested using the compatible portable environment.

A standard Fabric or Modrinth installation may not provide the runtime dependencies required for execution.

## Project Scope

OpenAesthetic is primarily intended for:

- Software preservation and historical documentation.
- Reverse-engineering research and technical analysis.
- Understanding client architecture and implementation techniques.
- Studying Java bytecode, native integrations, and obfuscation.

The repository should be treated as a technical reference rather than a fully maintainable or independently developed client.

## Legal Notice

OpenAesthetic is an unofficial, third-party research project and is not affiliated with, sponsored by, or endorsed by the original Aesthetic Client developers.

The recovered materials originate from analysis of a distributed client artifact. Their inclusion in this repository does not imply ownership, authorization, or the transfer of intellectual property rights.

All original code, assets, trademarks, and other protected materials remain subject to the rights of their respective owners.

Any independently developed tools, documentation, or replacement implementations may be licensed separately, provided their authors hold the necessary rights.

**OpenAesthetic does not claim to provide the original development source code or an officially authorized open-source release.**
