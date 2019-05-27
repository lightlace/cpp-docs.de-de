---
title: /LTCG (Code zur Verknüpfungszeit generieren)
ms.date: 05/16/2019
f1_keywords:
- VC.Project.VCLinkerTool.LinkTimeCodeGeneration
- VC.Project.VCConfiguration.WholeProgramOptimization
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
- /ltcg
- VC.Project.VCCLCompilerTool.WholeProgramOptimization
helpviewer_keywords:
- link-time code generation in C++ linker
- /LTCG linker option
- -LTCG linker option
- LTCG linker option
ms.assetid: 788c6f52-fdb8-40c2-90af-4026ea2cf2e2
ms.openlocfilehash: a8f13c32593d1cfef690d63d506faf14490de02d
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837269"
---
# <a name="ltcg-link-time-code-generation"></a>/LTCG (Code zur Verknüpfungszeit generieren)

Verwenden Sie **/LTCG**, um die Optimierung eines gesamten Programms durchzuführen oder profilgesteuerte Optimierungsinstrumentation (PGO) zu erstellen, Training durchzuführen und profilgesteuert optimierte Builds zu erstellen.

## <a name="syntax"></a>Syntax

> **/LTCG**[ **:** {**INCREMENTAL**|**NOSTATUS**|**STATUS**|**OFF**}]<br/>

Diese Optionen sind von Visual Studio 2015 an veraltet:

> **/LTCG:** {**PGINSTRUMENT**|**PGOPTIMIZE**|**PGUPDATE**}<br/>

### <a name="arguments"></a>Argumente

**INCREMENTAL**<br/>
(Optional) Gibt an, dass der Linker Optimierung des gesamten Programms oder Link-Zeitcodegenerierung (LTCG, Link-Time Code Generation) nur auf die von einer Bearbeitung betroffenen Dateien anwendet, statt auf das gesamte Projekt. Standardmäßig ist dieses Flag nicht gesetzt, wenn **/LTCG** angegeben wird, und das gesamte Projekt wird mithilfe der Optimierung gesamter Programme gelinkt.

**NOSTATUS** &#124; **STATUS**<br/>
(Optional) Gibt an, ob der Linker eine Statusanzeige anzeigt, die darstellt, welcher Prozentsatz des Links abgeschlossen ist. Standardmäßig werden diese Statusinformationen nicht angezeigt.

**OFF**<br/>
(Optional) Deaktiviert die Codegenerierung zur Verknüpfungszeit. Dieses Verhalten ist genau so, wenn **/LTCG** an der Befehlszeile nicht angegeben wird.

**PGINSTRUMENT**<br/>
(Optional) Diese Optionen sind von Visual Studio 2015 an veraltet. Verwenden Sie stattdessen **/LTCG** und [/GENPROFILE oder /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md), um einen instrumentierten Build für die profilgesteuerte Optimierung zu erstellen. Die Daten, die in instrumentierten Ausführungen gesammelt werden, werden zum Erstellen eines optimierten Images verwendet. Weitere Informationen finden Sie unter [Profilgesteuerte Optimierungen](../profile-guided-optimizations.md). Die Kurzform dieser Option lautet **/LTCG:PGI**.

**PGOPTIMIZE**<br/>
(Optional) Diese Optionen sind von Visual Studio 2015 an veraltet. Verwenden Sie stattdessen **/LTCG** und [/USEPROFILE](useprofile.md), um ein optimiertes Image zu erstellen. Weitere Informationen finden Sie unter [Profilgesteuerte Optimierungen](../profile-guided-optimizations.md). Die Kurzform dieser Option lautet **/LTCG:PGO**.

**PGUPDATE**<br/>
(Optional) Diese Optionen sind von Visual Studio 2015 an veraltet. Verwenden Sie stattdessen **/LTCG** und **/USEPROFILE**, um ein optimiertes Image erneut zu erstellen. Weitere Informationen finden Sie unter [Profilgesteuerte Optimierungen](../profile-guided-optimizations.md). Die Kurzform dieser Option lautet **/LTCG:PGU**.

## <a name="remarks"></a>Anmerkungen

Die Option **/LTCG** weist den Linker an, den Compiler aufzurufen und die Optimierung des gesamten Programms auszuführen. Alternativ können Sie auch eine profilgesteuerte Optimierung ausführen. Weitere Informationen finden Sie unter [Profilgesteuerte Optimierungen](../profile-guided-optimizations.md).

Abgesehen von den folgenden Ausnahmen, können Sie der PGO-Kombination aus **/LTCG** und **/USEPROFILE** keine Linkeroptionen hinzufügen, die in der vorherigen PGO-Initialisierungskombination der Optionen **/LTCG** und **/GENPROFILE** noch nicht angegeben waren:

- [/BASE](base-base-address.md)

- [/FIXED](fixed-fixed-base-address.md)

- **/LTCG**

- [/MAP](map-generate-mapfile.md)

- [/MAPINFO](mapinfo-include-information-in-mapfile.md)

- [/NOLOGO](nologo-suppress-startup-banner-linker.md)

- [/OUT](out-output-file-name.md)

- [/PGD](pgd-specify-database-for-profile-guided-optimizations.md)

- [/PDB](pdb-use-program-database.md)

- [/PDBSTRIPPED](pdbstripped-strip-private-symbols.md)

- [/STUB](stub-ms-dos-stub-file-name.md)

- [/VERBOSE](verbose-print-progress-messages.md)

Alle Linkeroptionen, die zusammen mit den Optionen **/LTCG** und **/GENPROFILE** zum Initialisieren von PGO angegeben werden, müssen beim Erstellen von Builds mithilfe von **/LTCG** und **/USEPROFILE** nicht angegeben werden; sie gelten implizit.

Im Rest dieses Themas wird **/LTCG** im Zusammenhang mit der Codegenerierung zur Verknüpfungszeit erörtert.

**/LTCG** ist mit [/GL](gl-whole-program-optimization.md) impliziert.

Der Linker ruft die Codegenerierung zur Verknüpfungszeit auf, wenn ihm ein Modul, das mithilfe von **/GL** kompiliert wurde, oder ein MSIL-Modul übergeben wird (siehe [.netmodule-Dateien als Linkereingabe](netmodule-files-as-linker-input.md)). Wenn Sie **/LTCG** beim Übergeben von **/GL** oder von MSIL-Modulen an den Linker nicht explizit angeben, erkennt der Linker dies möglicherweise, und startet das Linken mithilfe von **/LTCG** erneut. Geben Sie **/LTCG** beim Übergeben von **/GL** und MSIL-Modulen an den Linker explizit an, um eine möglichst schnelle Builderstellung zu erreichen.

Eine noch schnellere Leistung erreichen Sie mit **/LTCG:INCREMENTAL**. Diese Option weist den Linker an, nur die Menge der Dateien erneut zu optimieren, die von einer Änderung der Quelldatei betroffen sind, statt des gesamten Projekts. Dadurch kann sich die erforderliche Linkzeit erheblich verringern. Dies ist nicht die gleiche Option wie inkrementelles Linken.

**/LTCG** ist für die Verwendung mit [/INCREMENTAL](incremental-link-incrementally.md).

Wenn **/LTCG** zum Linken von Modulen verwendet wird, die mithilfe von [/Og](og-global-optimizations.md), [/O1](o1-o2-minimize-size-maximize-speed.md), [/O2](o1-o2-minimize-size-maximize-speed.md) oder [/Ox](ox-full-optimization.md) kompiliert wurden, werden die folgenden Optimierungen durchgeführt:

- Inlineoptimierung über verschiedene Module hinweg

- Interprozedurale Registerreservierung (nur bei 64-Bit-Betriebssystemen)

- Benutzerdefinierte Aufrufkonvention (nur x86)

- Geringe TLS-Verschiebung (nur x86)

- Doppelte Stapelausrichtung (nur x86)

- Verbesserte Speichereindeutigkeit (verbesserte Interferenzinformationen für globale Variablen und Eingabeparameter)

> [!NOTE]
> Der Linker bestimmt, welche Optimierungen zum Kompilieren der einzelnen Funktionen verwendet wurden, und wendet die gleichen Optimierungen zur Linkzeit an.

Die Verwendung von **/LTCG** und **/Ogt** bewirkt Optimierung der doppelten Ausrichtung.

Wenn **/LTCG** und **/Ogs** angegeben werden, wird keine doppelte Ausrichtung ausgeführt. Wenn die meisten Funktionen in einer Anwendung für beste Geschwindigkeit kompiliert wurden, einige Funktionen jedoch für geringste Größe kompiliert wurden (beispielsweise mithilfe des [optimize](../../preprocessor/optimize.md)-Pragmas), führt der Compiler eine doppelte Ausrichtung der Funktionen durch, deren Größe optimiert wurde, wenn sie Funktionen aufrufen, für die doppelte Ausrichtung erforderlich ist.

Wenn er alle Aufrufziele einer Funktion identifizieren kann, ignoriert der Compiler die expliziten Aufrufkonventionsmodifizierer der Funktion und versucht, die Aufrufkonvention der Funktion zu optimieren:

- Übergeben von Parametern in Registern

- Neuanordnen von Parametern zur Ausrichtung

- Entfernen nicht verwendeter Parameter

Wenn eine Funktion über einen Funktionszeiger oder von außerhalb eines Moduls aufgerufen wird, das mithilfe von **/GL** kompiliert wurde, versucht der Compiler nicht, die Aufrufkonvention der Funktion zu optimieren.

> [!NOTE]
> Wenn Sie **/LTCG** verwenden und `mainCRTStartup` neu definieren, kann bei Ihrer Anwendung nicht vorhersehbares Verhalten auftreten, das mit Benutzercode zusammenhängt, der vor der Initialisierung globaler Objekte ausgeführt wird. Es gibt drei Möglichkeiten, dieses Problem zu beheben: Definieren Sie `mainCRTStartup` nicht neu, kompilieren Sie die `mainCRTStartup` enthaltende Datei mit **/LTCG** oder initialisieren Sie globale Variablen und Objekte nach Möglichkeit statisch.

### <a name="ltcg-and-msil-modules"></a>/ LTCG und MSIL-Module

Mit [/GL](gl-whole-program-optimization.md) und [/clr](clr-common-language-runtime-compilation.md) kompilierte Module können als Eingabe für den Linker verwendet werden, wenn **/LTCG** angegeben ist.

- **/LTCG** kann native Objektdateien und gemischte native/verwaltete Objektdateien (die mithilfe von **/clr** kompiliert wurden) akzeptieren. Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet und werden in Visual Studio 2017 und höher nicht unterstützt.

- **/LTCG:PGI** akzeptiert keine nativen mit **/GL** und **/clr** kompilierten Module.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Lesen Sie dazu [Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die Eigenschaftenseite **Konfigurationseigenschaften** > **Allgemein** aus.

1. Ändern Sie die Eigenschaft **Optimierung des ganzen Programms** .

Sie können **/LTCG** auch auf bestimmte Builds anwenden, indem Sie **Build** > **Profilgesteuerte Optimierung** auf der Menüleiste oder eine der Optionen für die profilgesteuerte Optimierung im Kontextmenü des Projekts auswählen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>.

## <a name="see-also"></a>Siehe auch

- [MSVC-Linkerreferenz](linking.md)
- [MSVC-Linkeroptionen](linker-options.md)
