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
ms.openlocfilehash: 190174e1e2ac4d160140ddc54f9cc1c3a1b31709
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809027"
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

Die **/FC** Option impliziert wird, durch die **"/ Zi"**. Weitere Informationen zu **"/ Zi"**, finden Sie unter [/Z7, / Zi, / Zi (Debuginformationsformat)](z7-zi-zi-debug-information-format.md).

**/ FC** gibt vollständige Pfade in Kleinbuchstaben.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **erweitert** Eigenschaftenseite.

1. Ändern der **vollständige Pfade verwenden** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
