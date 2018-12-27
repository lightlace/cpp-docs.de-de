---
title: /OPT (Optimierungen)
ms.date: 05/18/2018
f1_keywords:
- VC.Project.VCLinkerTool.OptimizeReferences
- /opt
- VC.Project.VCLinkerTool.OptimizeForWindows98
- VC.Project.VCLinkerTool.EnableCOMDATFolding
- VC.Project.VCLinkerTool.OptimizeFolding
- VC.Project.VCLinkerTool.FoldingIterations
- VC.Project.VCLinkerTool.OptimizeFoldingIterations
helpviewer_keywords:
- LINK tool [C++], controlling optimizations
- -OPT linker option
- linker [C++], optimizations
- OPT linker option
- optimization, linker
- /OPT linker option
ms.assetid: 8f229863-5f53-48a8-9478-243a647093ac
ms.openlocfilehash: 1a6fa8b9c923ff697831c29b8004ce360baf7d77
ms.sourcegitcommit: ae2f71fe0d64f1a90ef722759fe93c82abc064ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/18/2018
ms.locfileid: "53587888"
---
# <a name="opt-optimizations"></a>/OPT (Optimierungen)

Steuert die Optimierungen, die während eines Builds von LINK ausgeführt werden.

## <a name="syntax"></a>Syntax

> **/ OPT:**{**REF** | **NOREF**}<br/>
> **/ OPT:**{**ICF**[**=**_Iterationen_] | **NOICF**}<br/>
> **/ OPT:**{**LBR** | **NOLBR**}

## <a name="arguments"></a>Argumente

**REF** &AMP;#124; **NOREF**

**/ OPT: REF** löscht Funktionen und Daten, die nie verwiesen werden; **NOREF** verfolgt, Funktionen und Daten, die nie verwiesen werden.

Wenn/OPT: REF aktiviert ist, entfernt LINK Unreferenzierte gepackte Funktionen und Daten, bekannt als *COMDATs*. Diese Optimierung ist als transitive COMDAT-Eliminierung bekannt. Die **/OPT: REF** Option deaktiviert auch die inkrementelle Verknüpfung.

Inlinefunktionen und Memberfunktionen, die innerhalb einer Klassendeklaration definiert sind immer COMDATs. Alle Funktionen in einer Objektdatei werden in COMDATs vorgenommen, wenn sie mithilfe von kompiliert wird die [/Gy](../../build/reference/gy-enable-function-level-linking.md) Option. Platzieren **const** Daten in COMDATs, Sie müssen es mit deklarieren `__declspec(selectany)`. Informationen zur Vorgehensweise beim Angeben von Daten zu entfernen oder zu falten, finden Sie unter [Selectany](../../cpp/selectany.md).

In der Standardeinstellung **/OPT: REF** vom Linker aktiviert ist, es sei denn, **NOREF** oder [/DEBUG](../../build/reference/debug-generate-debug-info.md) angegeben ist. Um diesen Standardwert überschreiben und Unreferenzierte COMDATs im Programm, geben Sie **NOREF**. Sie können die [/INCLUDE](../../build/reference/include-force-symbol-references.md) Option aus, um das Entfernen eines bestimmten Symbols zu überschreiben.

Wenn [/DEBUG](../../build/reference/debug-generate-debug-info.md) angegeben wird, der Standardwert für **"/ OPT"** ist **NOREF**, und alle Funktionen werden in der Abbildung beibehalten. Um diesen Standardwert überschreiben und einen Debugbuild zu optimieren, geben Sie **/OPT: REF**. Dies kann die Größe Ihrer ausführbaren Datei verringern, und es kann sein, dass eine nützliche Optimierung auch in der Debug-builds. Es wird empfohlen, dass Sie auch angeben, **NOICF** identische beibehalten Funktionen im Debugmodus wird erstellt. Dadurch wird es einfacher, in Funktionen, die andernfalls gefaltet würden, Stapelüberwachungen zu lesen und Haltepunkte festzulegen.

**ICF**\[**=**_Iterationen_] &#124; **NOICF**

Verwendung **ICF**\[**=**_Iterationen_], identische COMDAT-Faltung durchzuführen. Redundante COMDATs können aus der Linkerausgabe entfernt werden. Der optionale *Iterationen* Parameter gibt die Anzahl der Häufigkeit für das Durchlaufen der Symbole für Duplikate an. Die standardmäßige Anzahl von Iterationen ist 1. Zusätzliche Iterationen können mehr Duplikate auffinden, die bei der Faltung in vorherigen Iterationen unentdeckt blieben.

In der Standardeinstellung **/OPT: ICF** vom Linker aktiviert ist, es sei denn, **NOICF** oder [/DEBUG](../../build/reference/debug-generate-debug-info.md) angegeben ist. Um diesen Standardwert überschreiben, und verhindern, dass COMDATs im Programm gefaltet wird, geben Sie **NOICF**.

Sie müssen explizit angeben, in einem Debugbuild **/OPT: ICF** COMDAT-Faltung aktivieren. Aber da **/OPT: ICF** identische Daten oder Funktionen zusammenführen kann, kann sich die die in der stapelüberwachung angezeigten Funktionsnamen ändern. Sie können auch machen es unmöglich, Haltepunkte in bestimmten Funktionen festgelegt oder einige Daten im Debugger zu untersuchen und unterstützen Sie auf unerwartete Funktionen bei der Sie Schritt für Schritt den Code zu durchlaufen. Das Verhalten des Codes ist identisch, aber die Debugger-Präsentation kann sehr verwirrend sein. Aus diesem Grund nicht empfohlen, Sie verwenden **/OPT: ICF** im Debugmodus wird erstellt, es sei denn, die Vorteile von kompaktem Code die genannten Nachteile überwiegen.

> [!NOTE]
> Da **/OPT: ICF** kann dazu führen, dass dieselbe Adresse verschiedenen Funktionen oder schreibgeschützten Datenmembern zugewiesen werden (d. h. **const** Variablen beim Kompilieren mit **/Gy**), Sie können ein Programm unterbrechen, die von Funktionen oder schreibgeschützten Datenmembern eindeutigen Adressen abhängt. Weitere Informationen finden Sie unter [/Gy (Funktionslevel-Linking aktivieren)](../../build/reference/gy-enable-function-level-linking.md).

**LBR** &AMP;#124; **NOLBR**

Die **/OPT:LBR** und **/OPT:NOLBR** Optionen gelten nur für ARM-Binärdateien. Bestimmte Branchanweisungen von ARM-Prozessoren haben einen begrenzten Bereich. Wenn der Linker einen Sprung zu einer außerhalb des Gültigkeitsbereichs liegenden Adresse erkennt, ersetzt er die Zieladresse der Branchanweisung durch die Adresse einer „Codeinsel“, die eine Branchanweisung enthält, die auf das eigentliche Ziel abzielt. Sie können **/OPT:LBR** zum Optimieren der Erkennung von langen verzweigungsanweisungen und die Platzierung von zwischencodeinseln gesamtcodegröße zu minimieren. **/OPT:NOLBR** weist den Linker an, wie sie, ohne Optimierung erkannt werden codeinseln für lange verzweigungsanweisungen zu generieren.

In der Standardeinstellung die **/OPT:LBR** Option wird festgelegt, wenn keine inkrementelle Verlinkung aktiviert ist. Wenn Sie einen nicht inkrementellen Link, aber keine langen branchoptimierungen möchten, geben Sie **/OPT:NOLBR**. Die **/OPT:LBR** Option deaktiviert die inkrementelle Verknüpfung.

## <a name="remarks"></a>Hinweise

Wenn Sie in der Befehlszeile verwendet wird, der Linker standardmäßig **/OPT: REF, ICF LBR**. Wenn **/DEBUG** angegeben ist, wird der Standardwert ist **NOREF, NOICF, NOLBR**.

Die **"/ OPT"** Optimierungen in der Regel die Abbildgröße zu verringern, und beschleunigen die programmausführung. Diese Verbesserungen können in größeren Programmen beträchtlich sein, ist sie standardmäßig für Retail-Builds aktiviert sind.

Linker Optimierung nimmt zusätzliche Zeit voraus, aber der optimierte Code speichert auch die Zeit, wenn der Linker verfügt über weniger umsetzungen zu korrigieren und erstellt ein kleineres endgültige Bild, und sparen Sie sogar noch mehr Zeit er weniger Debuginformationen hat zu verarbeiten und in die PDB-Datei geschrieben. Wenn Optimierung aktiviert ist, kann dies ein Link schnellere insgesamt führen wie die kleine zusätzliche Kosten bei der Analyse möglicherweise werden mehr als ausgeglichen, die mit der Zeit, die einsparungen bei den Linker kleinere Binärdateien bewegt.

Die **"/ OPT"** Argumente können zusammen angegeben werden, durch Kommas getrennt. Beispielsweise anstelle von **/OPT: REF NOICF**, können Sie angeben, **/OPT: REF, NOICF**.

Können Sie die [/VERBOSE](../../build/reference/verbose-print-progress-messages.md) Linkeroption, um die Funktionen, die entfernt werden, finden Sie unter **/OPT: REF** sowie Funktionen, die von gefalteten **/OPT: ICF**.

Die **"/ OPT"** Argumente werden häufig für Projekte erstellt wurden, mithilfe von festgelegt die **neues Projekt** Dialogfeld in der Visual Studio-IDE, in der Regel über unterschiedliche Werte für die Debug- und Releasekonfigurationen. Wenn kein Wert für diese Optionen des Linkers in Ihrem Projekt festgelegt ist, können Sie die Standardeinstellungen für das Projekt, abrufen, die sich von den Standardwerten, die vom Linker in der Befehlszeile verwendet werden können.

### <a name="to-set-the-opticf-or-optref-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie die OPT:ICF- oder OPT:REF-Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Optimierung** Eigenschaftenseite.

1. Ändern Sie eine der folgenden Eigenschaften:

   - **COMDAT-Faltung aktivieren**

   - **Verweise**

### <a name="to-set-the-optlbr-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie die OPT:LBR-Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Option in **zusätzliche Optionen**:

   `/opt:lbr` oder `/opt:nolbr`

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe die Eigenschaften <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A>.

## <a name="see-also"></a>Siehe auch

- [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)
- [Linkeroptionen](../../build/reference/linker-options.md)
