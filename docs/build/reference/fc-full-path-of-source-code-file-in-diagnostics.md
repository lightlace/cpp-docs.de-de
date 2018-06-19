---
title: -FC (vollständiger Pfad der Quellcodedatei in Diagnose) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.UseFullPaths
- /FC
dev_langs:
- C++
helpviewer_keywords:
- /FC compiler option [C++]
- -FC compiler option [C++]
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4a721b6887b6c5c07d96a79b06f05e6d7855250b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373204"
---
# <a name="fc-full-path-of-source-code-file-in-diagnostics"></a>/FC (Vollständiger Pfad der Quellcodedatei in Diagnostik)

Bewirkt, dass den Compiler den vollständigen Pfad der Quellcodedateien, die an den Compiler bei der Diagnose übergebene anzeigen.

## <a name="syntax"></a>Syntax

> /FC

## <a name="remarks"></a>Hinweise

Betrachten Sie das folgende Codebeispiel:

```cpp
// compiler_option_FC.cpp
int main( ) {
   int i   // C2143
}
```

Ohne **/FC**, die Diagnosetext würde diese Diagnosetext ähnelt:

- compiler_option_FC.cpp(5): Fehler C2143: Syntaxfehler: Fehlender ";" vor "}"

Mit **/FC**, die Diagnosetext würde diese Diagnosetext ähnelt:

- c:\test\compiler_option_FC.cpp(5): Fehler C2143: Syntaxfehler: Fehlender ";" vor "}"

 **/ FC** ist auch erforderlich, wenn Sie den vollständigen Pfad eines Dateinamens finden Sie unter Verwendung möchten der &#95; &#95;Datei&#95; &#95; Makro. Finden Sie unter [vordefinierte Makros](../../preprocessor/predefined-macros.md) Weitere Informationen zu &#95; &#95;Datei&#95;&#95;.

Die **/FC** Option impliziert, durch die **/Zi**. Weitere Informationen zu **/Zi**, finden Sie unter ["/ Z7", / Zi, / Zi (Debuginformationsformat)](../../build/reference/z7-zi-zi-debug-information-format.md).

**/ FC** gibt vollständige Pfade in Kleinbuchstaben.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **erweitert** Eigenschaftenseite.

1. Ändern der **vollständige Pfade verwenden** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)   
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
