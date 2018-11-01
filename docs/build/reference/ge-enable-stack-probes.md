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
ms.openlocfilehash: 485a6a479f4d0d6c9e5eb745eda894a01f356e8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448931"
---
# <a name="ge-enable-stack-probes"></a>/Ge (Stapelüberprüfungen aktivieren)

Aktiviert stapelüberprüfungen für jeden Funktionsaufruf, der Speicher für lokale Variablen erforderlich ist.

## <a name="syntax"></a>Syntax

```
/Ge
```

## <a name="remarks"></a>Hinweise

Dieser Mechanismus ist nützlich, wenn Sie die Funktionalität des Prüfpunkts Stack neu schreiben. Es wird empfohlen, die Verwendung von [/GH (aktivieren _penter-Hookfunktion)](../../build/reference/gh-enable-penter-hook-function.md) statt die stapelüberprüfung umschreiben.

[/ GS (Steuerelement Stack überprüft Aufrufe)](../../build/reference/gs-control-stack-checking-calls.md) hat dieselbe Wirkung.

**/ Ge** ist veraltet; in Visual Studio 2005 generiert der Compiler automatisch stapelüberprüfung. Eine Liste der Ersetzte Compileroptionen, finden Sie unter **veraltete und entfernte Compileroptionen** in [Compiler Options Listed by Category](../../build/reference/compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)