---
title: /FC (Vollständiger Pfad der Quellcodedatei in Diagnostik)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.UseFullPaths
- /FC
helpviewer_keywords:
- /FC compiler option [C++]
- -FC compiler option [C++]
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
ms.openlocfilehash: 96809f09efd068b80f04a70d4356c1ceaf5f113c
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422480"
---
# <a name="fc-full-path-of-source-code-file-in-diagnostics"></a>/FC (Vollständiger Pfad der Quellcodedatei in Diagnostik)

Bewirkt, dass den Compiler den vollständigen Pfad der Quellcodedateien, die an den Compiler bei der Diagnose anzeigen.

## <a name="syntax"></a>Syntax

> /FC

## <a name="remarks"></a>Hinweise

Betrachten Sie das folgende Codebeispiel herunter:

```cpp
// compiler_option_FC.cpp
int main( ) {
   int i   // C2143
}
```

Ohne **/FC**, die Diagnosetext sieht etwa wie folgt Diagnose:

- compiler_option_FC.cpp(5): Fehler C2143: Syntaxfehler: Fehlender ';' vor '}'

Mit **/FC**, die Diagnosetext sieht etwa wie folgt Diagnose:

- c:\test\compiler_option_FC.cpp(5): Fehler C2143: Syntaxfehler: Fehlender ';' vor '}'

**/ FC** ist auch erforderlich, sollten Sie den vollständigen Pfad eines Dateinamens finden Sie unter Verwendung der &#95; &#95;Datei&#95; &#95; Makro. Finden Sie unter [Predefined Macros](../../preprocessor/predefined-macros.md) für Weitere Informationen zu &#95; &#95;Datei&#95;&#95;.

Die **/FC** Option impliziert wird, durch die **"/ Zi"**. Weitere Informationen zu **"/ Zi"**, finden Sie unter [/Z7, / Zi, / Zi (Debuginformationsformat)](../../build/reference/z7-zi-zi-debug-information-format.md).

**/ FC** gibt vollständige Pfade in Kleinbuchstaben.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **erweitert** Eigenschaftenseite.

1. Ändern der **vollständige Pfade verwenden** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
