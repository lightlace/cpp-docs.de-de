---
title: /Zo (erweitertes optimiertes Debugging)
ms.date: 11/04/2016
f1_keywords:
- -Zo
- /Zo
helpviewer_keywords:
- Zo compiler option [C++]
- /Zo compiler option [C++]
- -Zo compiler option [C++]
ms.assetid: eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f
ms.openlocfilehash: 2fb64b0cc39d5b7ff0c96d3eae47197c455526f5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809937"
---
# <a name="zo-enhance-optimized-debugging"></a>/Zo (erweitertes optimiertes Debugging)

Generieren Sie erweiterte Debuginformationen für optimierten Code in Nicht-Debugbuilds.

## <a name="syntax"></a>Syntax

```cpp
/Zo[-]
```

## <a name="remarks"></a>Hinweise

Die **/zo** -Compilerschalter generiert erweiterte Debuginformationen für optimierten Code. Bei der Optimierung können Register für lokale Variablen verwendet, Code neu angeordnet, Schleifen vektorisiert und Inline-Funktionsaufrufe verwendet werden. Diese Optimierungen können die Beziehung zwischen dem Quellcode und dem kompilierten Objektcode verbergen. Die **/zo** -Schalter weist den Compiler an, um zusätzliche Debuginformationen für lokale Variablen und Inlinefunktionen zu generieren. Verwenden, um Variablen in finden Sie unter den **"Auto"**, **"lokal"**, und **Watch** Windows beim Durchlaufen von optimiertem Code in Visual Studio-Debugger. Darüber hinaus können Stapelüberwachungen Inlinefunktionen im WinDBG-Debugger anzeigen. Debug-Builds, die Optimierungen deaktiviert haben ([/Od](od-disable-debug.md)) benötigen Sie nicht die zusätzliche Debuginformationen generiert, wenn **/zo** angegeben ist. Verwenden der **/zo** Switch Releasekonfigurationen mit aktivierter Optimierung zu debuggen. Weitere Informationen zu optimierungsschaltern finden Sie unter [/o-Optionen (Code optimieren)](o-options-optimize-code.md). Die **/zo** Option ist standardmäßig aktiviert, in Visual Studio bei der Angabe von Debuginformationen mit **"/ Zi"** oder **"/ Z7"**. Geben Sie **/Zo-** diese Compileroption explizit zu deaktivieren.

Die **/zo** Befehlszeilenoption ab, die in Visual Studio 2013 Update 3 verfügbar und ersetzt den zuvor nicht dokumentierten **/d2Zi+** wechseln.

### <a name="to-set-the-zo-compiler-option-in-visual-studio"></a>So legen Sie die /Zo-Compileroption in Visual Studio fest

1. Öffnen der **Eigenschaftenseiten** im Dialogfeld für das Projekt. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften**, **C/C++-** Ordner.

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite.

1. Ändern der **zusätzliche Optionen** Eigenschaft sollen `/Zo` und wählen Sie dann **OK**.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/O-Optionen (Code optimieren)](o-options-optimize-code.md)<br/>
[/Z7, /Zi, /ZI (Debuginformationsformat)](z7-zi-zi-debug-information-format.md)<br/>
[Bearbeiten und Fortfahren](/visualstudio/debugger/edit-and-continue)
