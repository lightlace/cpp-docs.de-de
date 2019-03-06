---
title: /Od (Deaktivieren (Debuggen))
ms.date: 11/04/2016
f1_keywords:
- /od
helpviewer_keywords:
- no optimizations
- fast compiling
- /Od compiler option [C++]
- disable optimizations
- Od compiler option [C++]
- -Od compiler option [C++]
- disable (debug) compiler option [C++]
ms.assetid: b1ac31b7-e086-4eeb-be5e-488f7513f5f5
ms.openlocfilehash: 386113c7926085aa7e82e23768556372014a8cc8
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426250"
---
# <a name="od-disable-debug"></a>/Od (Deaktivieren (Debuggen))

Deaktiviert alle Optimierungen im Programm und beschleunigt die Kompilierung.

## <a name="syntax"></a>Syntax

```
/Od
```

## <a name="remarks"></a>Hinweise

Diese Option ist die Standardeinstellung. Da **/Od** unterdrückt die Verschiebung von Code, es vereinfacht das Debuggen. Weitere Informationen zu Compileroptionen für das Debuggen, finden Sie unter [/Z7, / Zi, / Zi (Debuginformationsformat)](../../build/reference/z7-zi-zi-debug-information-format.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **Optimierung** Eigenschaftenseite.

1. Ändern der **Optimierung** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>Siehe auch

[/O-Optionen (Code optimieren)](../../build/reference/o-options-optimize-code.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[/Z7, /Zi, /ZI (Debuginformationsformat)](../../build/reference/z7-zi-zi-debug-information-format.md)
