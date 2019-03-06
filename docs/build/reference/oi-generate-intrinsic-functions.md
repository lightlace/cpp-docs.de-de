---
title: /Oi (Systeminterne Funktionen erstellen)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableIntrinsicFunctions
- /oi
- VC.Project.VCCLWCECompilerTool.EnableIntrinsicFunctions
helpviewer_keywords:
- Oi compiler option [C++]
- intrinsic functions, generate
- /Oi compiler option [C++]
- -Oi compiler option [C++]
- generate intrinsic functions compiler option [C++]
ms.assetid: fa4a3bf6-0ed8-481b-91c0-add7636132b4
ms.openlocfilehash: 1dc7f5f183e7dffb65c31ebb9bc47b30776b81e3
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422116"
---
# <a name="oi-generate-intrinsic-functions"></a>/Oi (Systeminterne Funktionen erstellen)

Eine Funktion mit systeminterne oder sonstige spezielle Formen der Funktion aufgerufen wird, mit denen Ihre Anwendung ersetzt werden schneller ausgeführt.

## <a name="syntax"></a>Syntax

```
/Oi[-]
```

## <a name="remarks"></a>Hinweise

Programme, die systeminterne Funktionen zu verwenden sind schneller auf, da sie nicht den Mehraufwand der Funktionsaufrufe müssen, jedoch möglicherweise ein größeres aufgrund des zusätzlich erstellten Codes.

Finden Sie unter [systeminterne](../../preprocessor/intrinsic.md) für Weitere Informationen, die für die Funktionen systeminterne Formen haben.

**/ Oi** ist nur eine Anforderung an den Compiler einige Funktionsaufrufe durch systeminterne Funktionen; ersetzt der Compiler möglicherweise rufen Sie die Funktion (und nicht durch eine systeminterne Funktion ersetzt den Funktionsaufruf) Wenn sie eine bessere Leistung führt.

**X86 bestimmte**

Die systeminternen Gleitkommafunktionen nicht speziellen Überprüfungen auf der Eingabewerten ausgeführt und so funktionieren in eingeschränkte Bereiche der Eingabe und verfügen über unterschiedliche Ausnahmebehandlung und begrenzungsbedingungen als die Bibliotheksroutinen mit dem gleichen Namen. Mit der echten systeminternen Formen impliziert, Verlust von IEEE-Ausnahmebehandlung und den Verlust von `_matherr` und `errno` Funktionalität; letztere impliziert den Verlust der ANSI-Konformität. Allerdings die systeminternen Formen können erheblich beschleunigen, Gleitkomma-Intensive Programme, und bei vielen Programmen ist die Konformitätsprobleme wenig praktischen Wert sind.

Sie können die [Za](../../build/reference/za-ze-disable-language-extensions.md) -Compileroption verwenden, um die Generierung von echten systeminternen Gleitkommaoptionen zu überschreiben. In diesem Fall werden die Funktionen als Bibliotheksroutinen erzeugt, die Argumente direkt an den Gleitkommachip übergeben, statt sie auf dem Programmstapel abzulegen.

**END X86 bestimmte**

Sie auch verwenden, [systeminterne](../../preprocessor/intrinsic.md) zum intrinsische Funktionen erstellen oder [-Funktion (C++)](../../preprocessor/function-c-cpp.md) um einen Funktionsaufruf explizit zu erzwingen.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **Optimierung** Eigenschaftenseite.

1. Ändern der **systeminterne Funktionen aktivieren** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableIntrinsicFunctions%2A>.

## <a name="see-also"></a>Siehe auch

[/O-Optionen (Code optimieren)](../../build/reference/o-options-optimize-code.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[Intrinsische Compilerfunktionen](../../intrinsics/compiler-intrinsics.md)
