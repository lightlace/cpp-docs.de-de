---
title: / LTCG (Link-Time Code Generation) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: 0e60bb086adbb1c573b21cafb54c61203c888e9a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725166"
---
# <a name="ltcg-link-time-code-generation"></a>/LTCG (Code zur Verknüpfungszeit generieren)

Verwendung **"/ LTCG"** programmübergreifende Optimierung durchführen oder auf Profilgesteuerte Optimierung (PGO)-Instrumentation erstellen, führen Sie die Schulung und erstellen Sie mit profilgesteuerter optimierte Builds.

## <a name="syntax"></a>Syntax

> **/LTCG**[**:**{**INCREMENTAL**|**NOSTATUS**|**STATUS**|**OFF**}]<br/>

Diese Optionen sind ab Visual Studio 2015 veraltet:

> **/ LTCG:**{**PGINSTRUMENT**|**PGOPTIMIZE**|**PGUPDATE**}<br/>

### <a name="arguments"></a>Argumente

**INKREMENTELLE**<br/>
(Optional) Gibt an, dass der Linker ganzen Programms Optimierung oder Link zeitcodegenerierung (LTCG) nur für den Satz von Dateien, die von einer Bearbeitung, statt des gesamten Projekts betroffen sind gilt. Standardmäßig dieses Flag nicht festgelegt, wenn **"/ LTCG"** angegeben ist, und das gesamte Projekt mit der Optimierung des ganzen Programms verknüpft ist.

**NOSTATUS** &AMP;#124; **STATUS**<br/>
(Optional) Gibt an, ob der Linker eine Statusanzeige, die anzeigt angezeigt, welcher Prozentsatz des Links abgeschlossen ist. Standardmäßig wird diese Statusinformationen nicht angezeigt.

**OFF**<br/>
(Optional) Deaktiviert die Link-zeitcodegenerierung. Dieses Verhalten ist identisch **"/ LTCG"** in der Befehlszeile nicht angegeben ist.

**PGINSTRUMENT**<br/>
(Optional) Diese Option ist ab Visual Studio 2015 veraltet. Verwenden Sie stattdessen **"/ LTCG"** und [/genprofile oder/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) um einen instrumentierten Build für die profilgesteuerte Optimierung zu generieren. Die Daten, die von den instrumentierten Ausführungen erfasst werden, werden zum Erstellen eines optimierten Images verwendet. Weitere Informationen finden Sie unter [Profilgesteuerte Optimierung](profile-guided-optimizations.md). Die Kurzform dieser Option ist **/LTCG: PGI**.

**PGOPTIMIZE**<br/>
(Optional) Diese Option ist ab Visual Studio 2015 veraltet. Verwenden Sie stattdessen **"/ LTCG"** und [/USERPROFILE angegeben](useprofile.md) zum Erstellen eines optimierten Images. Weitere Informationen finden Sie unter [Profilgesteuerte Optimierung](../../build/reference/profile-guided-optimizations.md). Die Kurzform dieser Option ist **/LTCG: PGO**.

**PGUPDATE**<br/>
(Optional) Diese Option ist ab Visual Studio 2015 veraltet. Verwenden Sie stattdessen **"/ LTCG"** und **/USERPROFILE angegeben** ein optimiertes Images neu erstellen. Weitere Informationen finden Sie unter [Profilgesteuerte Optimierung](../../build/reference/profile-guided-optimizations.md). Die Kurzform dieser Option ist **pgu**.

## <a name="remarks"></a>Hinweise

Die **"/ LTCG"** -Option weist den Linker an, den Compiler aufzurufen und die Optimierung des gesamten Programms auszuführen. Alternativ können Sie auch eine profilgesteuerte Optimierung ausführen. Weitere Informationen finden Sie unter [Profilgesteuerte Optimierung](../../build/reference/profile-guided-optimizations.md).

Mit den folgenden Ausnahmen, können keine hinzugefügt Optionen des Linkers die PGO-Kombination von **"/ LTCG"** und **/USERPROFILE angegeben** , wurden nicht angegeben, in der vorherigen PGO-initialisierungskombination der  **/ LTCG** und **/genprofile** Optionen:

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

Alle Linkeroptionen, die zusammen mit angegeben sind die **"/ LTCG"** und **/genprofile** Optionen zum Initialisieren von PGO müssen nicht angegeben werden, die beim Erstellen mit **"/ LTCG"** und **/USERPROFILE angegeben**; sie gelten implizit.

Im weiteren Verlauf dieses Artikels erläutert **"/ LTCG"** in Bezug auf die Link-zeitcodegenerierung.

**/ LTCG** ist impliziert, ["/ GL"](../../build/reference/gl-whole-program-optimization.md).

Der Linker Link-zeitcodegenerierung aufruft, wenn sie ein Modul übergeben wird, die mithilfe von kompiliert wurde **"/ GL"** oder ein MSIL-Modul (finden Sie unter [NETMODULE-Dateien als Linkereingabe](../../build/reference/netmodule-files-as-linker-input.md)). Wenn Sie nicht explizit angeben **"/ LTCG"** , wenn Sie übergeben **"/ GL"** oder MSIL-Modulen an den Linker, die der Linker schließlich erkennt dies und startet den Link **"/ LTCG"**. Geben Sie explizit **"/ LTCG"** , wenn Sie übergeben **"/ GL"** und MSIL-Modulen an den Linker möglichst schnelle Leistung.

Verwenden Sie für noch schnellere Leistung **/LTCG: inkrementelle**. Diese Option weist den Linker an, nur die Menge der Dateien erneut zu optimieren, die von einer Änderung der Quelldatei betroffen sind, statt des gesamten Projekts. Dadurch kann sich die erforderliche Linkzeit erheblich verringern. Dies ist nicht die gleiche Option als inkrementelles Verknüpfen.

**/LTCG** ist für die Verwendung mit [/INCREMENTAL](../../build/reference/incremental-link-incrementally.md).

Wenn **"/ LTCG"** wird verwendet, um mithilfe von kompilierten Modulen verknüpfen ["/ Og"](../../build/reference/og-global-optimizations.md), ["/ O1"](../../build/reference/o1-o2-minimize-size-maximize-speed.md), ["/ O2"](../../build/reference/o1-o2-minimize-size-maximize-speed.md), oder [/Ox](../../build/reference/ox-full-optimization.md), folgende Optimierungen werden ausgeführt:

- Inlineoptimierung über verschiedene Module hinweg

- Interprozedurale Registerreservierung (nur bei 64-Bit-Betriebssystemen)

- Benutzerdefinierte Aufrufkonvention (nur x86)

- Geringe TLS-Verschiebung (nur x86)

- Doppelte Stapelausrichtung (nur x86)

- Verbesserte Speichereindeutigkeit (verbesserte Interferenzinformationen für globale Variablen und Eingabeparameter)

> [!NOTE]
> Der Linker bestimmt, welche Optimierungen zum Kompilieren der einzelnen Funktionen verwendet wurden, und wendet die gleichen Optimierungen zur Linkzeit an.

Mithilfe von **"/ LTCG"** und **Ogt** doppelter Ausrichtung Optimierung führt.

Wenn **"/ LTCG"** und **/Ogs verwendet** angegeben ist, erfolgt keine doppelte Ausrichtung. Wenn die meisten Funktionen in einer Anwendung auf Geschwindigkeit, mit einige hinsichtlichgröße kompiliert Funktionen kompiliert werden (z. B. durch Verwendung der [optimieren](../../preprocessor/optimize.md) Pragma), richtet der Compiler Double-Wert-Funktionen, die für die Größe optimiert werden, wenn sie aufrufen Funktionen, die doppelte Ausrichtung zu erfordern.

Wenn er alle Aufrufziele einer Funktion identifizieren kann, ignoriert der Compiler die expliziten Aufrufkonventionsmodifizierer der Funktion und versucht, die Aufrufkonvention der Funktion zu optimieren:

- Übergeben von Parametern in Registern

- Neuanordnen von Parametern zur Ausrichtung

- Entfernen nicht verwendeter Parameter

Wenn eine Funktion über einen Funktionszeiger aufgerufen wird oder wenn eine Funktion von außerhalb eines Moduls aufgerufen wird, die mithilfe von kompiliert wird **"/ GL"**, versucht der Compiler nicht, die Aufrufkonvention der Funktion zu optimieren.

> [!NOTE]
> Bei Verwendung von **"/ LTCG"** und neu definieren `mainCRTStartup`, Ihre Anwendung kann zu unvorhersehbarem Verhalten, die für Benutzercode, der ausgeführt wird, bevor der globale Objekte initialisiert werden, bezieht sich haben. Es gibt drei Möglichkeiten, dieses Problem zu beheben: definieren nicht neu `mainCRTStartup`, kompilieren Sie die Datei mit nicht `mainCRTStartup` mit **"/ LTCG"**, oder initialisieren Sie globale Variablen und Objekte statisch.

### <a name="ltcg-and-msil-modules"></a>/ LTCG und MSIL-Module

Mit [/GL](../../build/reference/gl-whole-program-optimization.md) und [/clr](../../build/reference/clr-common-language-runtime-compilation.md) kompilierte Module können als Eingabe für den Linker verwendet werden, wenn **/LTCG** angegeben ist.

- **/ LTCG** akzeptiert systemeigene Objektdateien und gemischte systemeigene/verwaltete Objektdateien (kompiliert mit **"/ CLR"**). Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

- **/ LTCG: PGI** akzeptiert keine native Modulen, die mit kompiliert **"/ GL"** und **"/ CLR"**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **allgemeine** Eigenschaftenseite.

1. Ändern Sie die Eigenschaft **Optimierung des ganzen Programms** .

Sie können auch anwenden **"/ LTCG"** auf bestimmte Builds durch Auswahl **erstellen** > **Profilgesteuerte Optimierung** in der Menüleiste oder Auswählen eines Profils Profilgesteuerte Optimierungsoptionen im Kontextmenü für das Projekt.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>.

## <a name="see-also"></a>Siehe auch

- [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)
- [Linkeroptionen](../../build/reference/linker-options.md)
