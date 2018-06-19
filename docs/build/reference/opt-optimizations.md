---
title: / OPT (Optimierungen) | Microsoft Docs
ms.custom: ''
ms.date: 05/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.OptimizeReferences
- /opt
- VC.Project.VCLinkerTool.OptimizeForWindows98
- VC.Project.VCLinkerTool.EnableCOMDATFolding
- VC.Project.VCLinkerTool.OptimizeFolding
- VC.Project.VCLinkerTool.FoldingIterations
- VC.Project.VCLinkerTool.OptimizeFoldingIterations
dev_langs:
- C++
helpviewer_keywords:
- LINK tool [C++], controlling optimizations
- -OPT linker option
- linker [C++], optimizations
- OPT linker option
- optimization, linker
- /OPT linker option
ms.assetid: 8f229863-5f53-48a8-9478-243a647093ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc9f7f66b9bd0ee2c0da65d17eac33e1cbc8c316
ms.sourcegitcommit: da7b7533d1a4dc141cc0f09149e4e4196f2fe329
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
ms.locfileid: "34463104"
---
# <a name="opt-optimizations"></a>/OPT (Optimierungen)

Steuert die Optimierungen, die während eines Builds von LINK ausgeführt werden.

## <a name="syntax"></a>Syntax

> **/ OPT:**{**REF** | **NOREF**}<br/>
> **/ OPT:**{**ICF**[**=**_Iterationen_] | **NOICF**}<br/>
> **/ OPT:**{**LBR** | **NOLBR**}

## <a name="arguments"></a>Argumente

**REF** &AMP;#124; **NOREF**

**/ OPT: REF** löscht Funktionen und Daten, die nie verwiesen werden; **NOREF** bleiben Funktionen und Daten, die nie verwiesen wird.

Wenn/OPT: REF aktiviert ist, entfernt LINK Unreferenzierte gepackte Funktionen und Daten, die als bekannt *COMDATs*. Diese Optimierung ist als transitive COMDAT-Eliminierung bekannt. Die **/OPT: REF** Option auch wird inkrementelles Verknüpfen deaktiviert.

Inlinefunktionen und Memberfunktionen, die innerhalb einer Klassendeklaration definiert sind immer COMDATs. Alle Funktionen in einer Objektdatei in COMDATs vorgenommen werden, wenn sie mithilfe von kompiliert ist die [/Gy](../../build/reference/gy-enable-function-level-linking.md) Option. Platzieren **const** Daten in COMDATs, Sie müssen ihn mit deklarieren `__declspec(selectany)`. Informationen über das Angeben von Daten zu entfernen oder zu Faltung finden Sie unter [Selectany](../../cpp/selectany.md).

Standardmäßig **/OPT: REF** vom Linker aktiviert ist, es sei denn, **NOREF** oder [/DEBUG](../../build/reference/debug-generate-debug-info.md) angegeben ist. Um diesen Standardwert überschreiben und Unreferenzierte COMDATs im Programm beizubehalten, geben Sie **NOREF**. Sie können die [/INCLUDE](../../build/reference/include-force-symbol-references.md) Option aus, um das Entfernen eines bestimmten Symbols zu überschreiben.

Wenn [/DEBUG](../../build/reference/debug-generate-debug-info.md) angegeben wird, der Standardwert für **/OPT** ist **NOREF**, und alle Funktionen werden im Image beibehalten. Um diesen Standardwert überschreiben und einen Debugbuild zu optimieren, geben Sie **/OPT: REF**. Das Reduzieren der Größe Ihrer ausführbaren Datei, eine nützliche Optimierung selbst im Debug-Builds sein. Es wird empfohlen, dass Sie auch angeben, **/OPT:NOICF** identische beibehalten Funktionen im Debugmodus erstellt. Dadurch wird es einfacher, in Funktionen, die andernfalls gefaltet würden, Stapelüberwachungen zu lesen und Haltepunkte festzulegen.

**ICF**\[**=**_Iterationen_] &#124; **NOICF**

Verwendung **ICF**\[**=**_Iterationen_] um identische COMDAT-Faltung durchzuführen. Redundante COMDATs können aus der Linkerausgabe entfernt werden. Das optionale *Iterationen* Parameter gibt die Anzahl der erneuten Versuche zum Durchlaufen der Symbole für Duplikate an. Die Standardanzahl von Iterationen ist 1. Zusätzliche Iterationen können mehr Duplikate auffinden, die bei der Faltung in vorherigen Iterationen unentdeckt blieben.

Standardmäßig **/OPT: ICF** vom Linker aktiviert ist, es sei denn, **/OPT:NOICF** oder [/DEBUG](../../build/reference/debug-generate-debug-info.md) angegeben ist. Um diese Standardeinstellung zu überschreiben, und verhindern, dass COMDATs im Programm gefaltet wird, geben Sie **/OPT:NOICF**.

Sie müssen explizit angeben, in einem Debugbuild **/OPT: ICF** COMDAT-Faltung aktivieren. Aber da **/OPT: ICF** identische Daten oder Funktionen zusammenführen kann, kann es sich um die die in der stapelüberwachung angezeigten Funktionsnamen ändern. Sie können auch machen es unmöglich, Festlegen von Haltepunkten in bestimmten Funktionen oder einige Daten im Debugger überprüfen und können Sie unerwartete Funktionen berücksichtigen bei der Sie Schritt für Schritt durchlaufen des Codes. Das Verhalten des Codes ist identisch, aber die Debugger-Präsentation kann sehr verwirrend sein. Daher nicht empfehlenswert die Verwendung von **/OPT: ICF** im Debugmodus erstellt, es sei denn, die Vorteile von kompaktem Code die genannten Nachteile überwiegen.

> [!NOTE]
> Da **/OPT: ICF** kann dazu führen, dass die gleiche Adresse unterschiedlichen Funktionen oder schreibgeschützten Datenmembern zugewiesen werden (d. h. **const** Variablen, die beim Kompilieren mit **/Gy**), Sie können ein Programm auch, von denen eindeutige Adressen für Funktionen oder schreibgeschützte Datenmember abhängt. Weitere Informationen finden Sie unter [/Gy (Funktionslevel-Linking aktivieren)](../../build/reference/gy-enable-function-level-linking.md).

**LBR** &AMP;#124; **NOLBR**

Die **/OPT:LBR** und **/OPT:NOLBR** Optionen gelten nur für ARM-Binärdateien. Bestimmte Branchanweisungen von ARM-Prozessoren haben einen begrenzten Bereich. Wenn der Linker einen Sprung zu einer außerhalb des Gültigkeitsbereichs liegenden Adresse erkennt, ersetzt er die Zieladresse der Branchanweisung durch die Adresse einer „Codeinsel“, die eine Branchanweisung enthält, die auf das eigentliche Ziel abzielt. Sie können **/OPT:LBR** optimiert die Erkennung von langen verzweigungsanweisungen und die Platzierung von zwischencodeinseln gesamtcodegröße zu minimieren. **/OPT:NOLBR** weist den Linker an, wie sie, ohne Optimierung erkannt werden codeinseln für lange verzweigungsanweisungen zu generieren.

Wird standardmäßig die **/OPT:LBR** Option wird festgelegt, wenn keine inkrementelle Verlinkung aktiviert ist. Wenn Sie einen nicht inkrementellen Link, aber keine langen branchoptimierungen möchten, geben Sie **/OPT:NOLBR**. Die **/OPT:LBR** -Option wird inkrementelles Verknüpfen deaktiviert.

## <a name="remarks"></a>Hinweise

Wenn in der Befehlszeile verwendet wird, verwendet der Linker standardmäßig **/OPT: REF, ICF, LBR**. Wenn **/DEBUG** angegeben ist, wird der Standardwert ist **NOREF NOICR, NOLBR**.

Die **/OPT** Optimierungen im Allgemeinen die Imagegröße zu verringern und beschleunigen die programmausführung. Diese Verbesserungen können erheblich größere Programme sein, ist sie standardmäßig für retailbuilds aktiviert sind.

Linker Optimierung nimmt zusätzliche Zeit voraus, aber der optimierte Code speichert auch die Zeit, wenn der Linker hat weniger umsetzungen zu korrigierenden und ein kleineres endgültige Image erstellt, und es speichert auch mehr Zeit, er weniger Debuginformationen hat zu verarbeiten und das Schreiben in die PDB-Datei. Wenn die netzwerkoptimierung aktiviert ist, kann dies zu einer schnelleren Link insgesamt führen wie die kleine zusätzliche Kosten in der Analyse möglicherweise werden mehr als Versatz von dem Zeitpunkt, zu speichereinsparungen Linker kleinere Binärdateien bewegt.

Die **/OPT** Argumente können zusammen angegeben werden, durch Kommas getrennt. Beispielsweise anstelle von **/OPT: REF /OPT:NOICF**, können Sie angeben, **/OPT: REF, NOICF**.

Sie können die [/VERBOSE](../../build/reference/verbose-print-progress-messages.md) Linkeroption, um die Funktionen, die entfernt werden, finden Sie unter **/OPT: REF** und Funktionen, die von gefalteten **/OPT: ICF**.

Die **/OPT** Argumente werden häufig für Projekte mit erstellt festgelegt die **neues Projekt** Dialogfeld in der Visual Studio-IDE und in der Regel haben unterschiedliche Werte für die Debug- und Releasekonfigurationen. Wenn kein Wert für diese Optionen des Linkers in Ihrem Projekt festgelegt ist, können die Standardeinstellungen für das Projekt, erhalten Sie die von den Standardwerten, die vom Linker in der Befehlszeile verwendet werden, unterschiedlich sein kann.

### <a name="to-set-the-opticf-or-optref-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie die OPT:ICF- oder OPT:REF-Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Optimierung** Eigenschaftenseite.

1. Ändern Sie eine der folgenden Eigenschaften:

   - **COMDAT-Faltung aktivieren**

   - **Verweise**

### <a name="to-set-the-optlbr-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie die OPT:LBR-Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Option im **Zusatzoptionen**:

   `/opt:lbr` oder `/opt:nolbr`

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe die Eigenschaften <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A>.

## <a name="see-also"></a>Siehe auch

- [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)
- [Linkeroptionen](../../build/reference/linker-options.md)
