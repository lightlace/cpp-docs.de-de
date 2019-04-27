---
title: /Ge (Stapelüberprüfungen aktivieren)
ms.date: 11/04/2016
f1_keywords:
- /ge
helpviewer_keywords:
- -Ge compiler option [C++]
- enable stack probes
- /Ge compiler option [C++]
- stack, stack probes
- stack probes
- stack checking calls
- Ge compiler option [C++]
ms.assetid: 4b54deae-4e3c-4bfa-95f3-ba23590f7258
ms.openlocfilehash: a785ec041370e0bcbb2ce8b698bfba89235a0a0c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292184"
---
# <a name="ge-enable-stack-probes"></a>/Ge (Stapelüberprüfungen aktivieren)

Aktiviert stapelüberprüfungen für jeden Funktionsaufruf, der Speicher für lokale Variablen erforderlich ist.

## <a name="syntax"></a>Syntax

```
/Ge
```

## <a name="remarks"></a>Hinweise

Dieser Mechanismus ist nützlich, wenn Sie die Funktionalität des Prüfpunkts Stack neu schreiben. Es wird empfohlen, die Verwendung von [/GH (aktivieren _penter-Hookfunktion)](gh-enable-penter-hook-function.md) statt die stapelüberprüfung umschreiben.

[/ GS (Steuerelement Stack überprüft Aufrufe)](gs-control-stack-checking-calls.md) hat dieselbe Wirkung.

**/ Ge** ist veraltet; in Visual Studio 2005 generiert der Compiler automatisch stapelüberprüfung. Eine Liste der Ersetzte Compileroptionen, finden Sie unter **veraltete und entfernte Compileroptionen** in [Compiler Options Listed by Category](compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
