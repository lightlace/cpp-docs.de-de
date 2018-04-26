---
title: / LTCG (Link-Time Code Generation) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.LinkTimeCodeGeneration
- VC.Project.VCConfiguration.WholeProgramOptimization
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
- /ltcg
- VC.Project.VCCLCompilerTool.WholeProgramOptimization
dev_langs:
- C++
helpviewer_keywords:
- link-time code generation in C++ linker
- /LTCG linker option
- -LTCG linker option
- LTCG linker option
ms.assetid: 788c6f52-fdb8-40c2-90af-4026ea2cf2e2
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8ac39babea0c36e9d5d120e1f5ca89e3f3dc014
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="ltcg-link-time-code-generation"></a>/LTCG (Code zur Verknüpfungszeit generieren)

Verwendung **/LTCG** zum Durchführen der Optimierung des gesamten Programms oder zum Instrumentation Profilgesteuerte Optimierung (PGO) zu erstellen, führen Sie die Schulung und erstellen die profilgesteuerte optimiert Builds.

## <a name="syntax"></a>Syntax

> **/LTCG**[**:**{**INCREMENTAL**|**NOSTATUS**|**STATUS**|**OFF**}]<br/>

Diese Optionen sind in Visual Studio 2015 ab veraltet:

> **/ LTCG:**{**PGINSTRUMENT**|**PGOPTIMIZE**|**PGUPDATE**}<br/>

### <a name="arguments"></a>Argumente

**INKREMENTELLE** (optional)<br/>
Gibt an, dass der Linker nur ganzen Programms Optimierungs- oder Link-Time-codegenerierung (zur linkzeit LTCG) auf den Satz der von einer Bearbeitung, statt des gesamten Projekts betroffenen Dateien anwendet. Standardmäßig dieses Flag nicht festgelegt, wenn **/LTCG** angegeben ist, und das gesamte Projekt wird mit Optimierung des gesamten Programms gelinkt.

**NOSTATUS** &#124; **STATUS** (optional)<br/>
Gibt an, ob der Linker eine Statusanzeige, die anzeigt ausgibt, welcher Prozentsatz des Linkvorgangs abgeschlossen ist. Standardmäßig wird diese Statusinformationen nicht angezeigt.

**DEAKTIVIERT** (optional)<br/>
Deaktiviert die Link-zeitcodegenerierung. Dieses Verhalten entspricht dem Verhalten wie beim **/LTCG** nicht in der Befehlszeile angegeben.

**PGINSTRUMENT** (optional)<br/>
Diese Option ist in Visual Studio 2015 ab veraltet. Verwenden Sie stattdessen **/LTCG** und [/genprofile oder/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) um einen instrumentierten Build für die profilgesteuerte Optimierung zu generieren. Die gesammelten Daten werden von den instrumentierten Ausführungen dient zum Erstellen eines optimierten Images. Weitere Informationen finden Sie unter [Profilgesteuerte Optimierung](profile-guided-optimizations.md). Die Kurzform dieser Option lautet **/LTCG: PGI**.

**PGOPTIMIZE** (optional)<br/>
Diese Option ist in Visual Studio 2015 ab veraltet. Verwenden Sie stattdessen **/LTCG** und [/useprofile](useprofile.md) zum Erstellen eines optimierten Images. Weitere Informationen finden Sie unter [Profilgesteuerte Optimierung](../../build/reference/profile-guided-optimizations.md). Die Kurzform dieser Option lautet **/LTCG: PGO**.

**PGUPDATE** (optional)<br/>
Diese Option ist in Visual Studio 2015 ab veraltet. Verwenden Sie stattdessen **/LTCG** und **/useprofile** ein optimiertes Images neu erstellt. Weitere Informationen finden Sie unter [Profilgesteuerte Optimierung](../../build/reference/profile-guided-optimizations.md). Die Kurzform dieser Option lautet **/LTCG: pgu**.

## <a name="remarks"></a>Hinweise

Die **/LTCG** Option weist den Linker an den Compiler aufzurufen und die Optimierung des gesamten Programms auszuführen. Alternativ können Sie auch eine profilgesteuerte Optimierung ausführen. Weitere Informationen finden Sie unter [Profilgesteuerte Optimierung](../../build/reference/profile-guided-optimizations.md).

Mit den folgenden Ausnahmen können Sie die profilgesteuerte Optimierung Kombination von Optionen des Linkers hinzufügen **/LTCG** und **/useprofile** , wurden nicht angegeben, in der vorherigen PGO Initialisierung Kombination von  **/ LTCG** und **/genprofile** Optionen:

- [/BASE](../../build/reference/base-base-address.md)

- [/FIXED](../../build/reference/fixed-fixed-base-address.md)

- **/LTCG**

- [/MAP](../../build/reference/map-generate-mapfile.md)

- [/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)

- [/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)

- [/OUT](../../build/reference/out-output-file-name.md)

- [/PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)

- [/PDB](../../build/reference/pdb-use-program-database.md)

- [/PDBSTRIPPED](../../build/reference/pdbstripped-strip-private-symbols.md)

- [/STUB](../../build/reference/stub-ms-dos-stub-file-name.md)

- [/VERBOSE](../../build/reference/verbose-print-progress-messages.md)

Alle Optionen des Linkers, die zusammen mit werden die **/LTCG** und **/genprofile** Optionen für die profilgesteuerte Optimierung initialisieren müssen nicht angegeben werden, wenn Sie mithilfe von erstellen **/LTCG** und **/Useprofile**; sie sind impliziert.

Im weiteren Verlauf dieses Artikels erörtert **/LTCG** im Hinblick auf die Link-zeitcodegenerierung.

**/ LTCG** ist impliziert [/GL](../../build/reference/gl-whole-program-optimization.md).

Der Linker wird Link-zeitcodegenerierung aufgerufen, wenn sie ein Modul übergeben wird, die mit kompiliert wurde **/GL** oder ein MSIL-Modul (finden Sie unter [NETMODULE-Dateien als Linkereingabe](../../build/reference/netmodule-files-as-linker-input.md)). Wenn Sie nicht explizit angeben **/LTCG** , wenn Sie übergeben **/GL** oder MSIL-Modulen an den Linker an, der Linker schließlich erkennt dies und neu gestartet wird die Verknüpfung mit **/LTCG**. Geben Sie explizit **/LTCG** , wenn Sie übergeben **/GL** und MSIL-Modulen an den Linker an, für die schnellstmögliche erstellen Leistung.

Verwenden Sie für schnellere Leistung **/LTCG: inkrementelle**. Diese Option weist den Linker an, nur die Menge der Dateien erneut zu optimieren, die von einer Änderung der Quelldatei betroffen sind, statt des gesamten Projekts. Dadurch kann sich die erforderliche Linkzeit erheblich verringern. Dies ist nicht die gleiche Option als inkrementelles Verknüpfen.

**/LTCG** ist für die Verwendung mit [/INCREMENTAL](../../build/reference/incremental-link-incrementally.md).

Wenn **/LTCG** wird verwendet, um mithilfe von kompilierten Module verknüpfen [/Og](../../build/reference/og-global-optimizations.md), [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), oder [/Ox](../../build/reference/ox-full-optimization.md), folgende Optimierungen werden ausgeführt:

- Inlineoptimierung über verschiedene Module hinweg

- Interprozedurale Registerreservierung (nur bei 64-Bit-Betriebssystemen)

- Benutzerdefinierte Aufrufkonvention (nur x86)

- Geringe TLS-Verschiebung (nur x86)

- Doppelte Stapelausrichtung (nur x86)

- Verbesserte Speichereindeutigkeit (verbesserte Interferenzinformationen für globale Variablen und Eingabeparameter)

> [!NOTE]
> Der Linker bestimmt, welche Optimierungen zum Kompilieren der einzelnen Funktionen verwendet wurden, und wendet die gleichen Optimierungen zur Linkzeit an.

Mit **/LTCG** und **Ogt** doppelter Ausrichtung Optimierung verursacht.

Wenn **/LTCG** und **/Ogs verwendet** angegeben ist, erfolgt keine doppelte Ausrichtung. Wenn die meisten Funktionen in einer Anwendung für Geschwindigkeit, einige Funktionen für die Größe kompiliert werden (z. B. mithilfe der [optimieren](../../preprocessor/optimize.md) Pragma), richtet der Compiler Double-Funktionen, die für die Größe optimiert werden, wenn sie aufrufen Funktionen, die doppelte Ausrichtung erfordern.

Wenn er alle Aufrufziele einer Funktion identifizieren kann, ignoriert der Compiler die expliziten Aufrufkonventionsmodifizierer der Funktion und versucht, die Aufrufkonvention der Funktion zu optimieren:

- Übergeben von Parametern in Registern

- Neuanordnen von Parametern zur Ausrichtung

- Entfernen nicht verwendeter Parameter

Wenn eine Funktion über einen Funktionszeiger aufgerufen wird oder wenn eine Funktion von außerhalb eines Moduls aufgerufen wird, die kompiliert wird **/GL**, versucht der Compiler nicht die Aufrufkonvention der Funktion zu optimieren.

> [!NOTE]
> Bei Verwendung von **/LTCG** und Neudefinition von `mainCRTStartup`, Ihre Anwendung kann zu unvorhersehbares Verhalten führen, die für Benutzercode beziehen, die ausgeführt wird, bevor der globale Objekte initialisiert werden müssen. Es gibt drei Möglichkeiten, dieses Problem zu beheben: definieren nicht neu `mainCRTStartup`, kompilieren Sie die Datei mit `mainCRTStartup` mit **/LTCG**, oder initialisieren Sie globale Variablen und Objekte statisch.

### <a name="ltcg-and-msil-modules"></a>/ LTCG und MSIL-Module

Mit [/GL](../../build/reference/gl-whole-program-optimization.md) und [/clr](../../build/reference/clr-common-language-runtime-compilation.md) kompilierte Module können als Eingabe für den Linker verwendet werden, wenn **/LTCG** angegeben ist.

- **/ LTCG** können akzeptiert systemeigene Objektdateien und gemischte systemeigene/verwaltete Objektdateien (kompiliert mit **"/ CLR"**). Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.

- **/ LTCG: PGI** akzeptiert keine native Modulen mit kompiliert **/GL** und **"/ CLR"**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **allgemeine** Eigenschaftenseite.

1. Ändern Sie die Eigenschaft **Optimierung des ganzen Programms** .

Sie können auch anwenden **/LTCG** auf bestimmte Builds durch Auswahl **erstellen** > **Profilgesteuerte Optimierung** in der Menüleiste oder Auswählen eines Profils Profilgesteuerte Optimierungsoptionen im Kontextmenü für das Projekt.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)<br/>
