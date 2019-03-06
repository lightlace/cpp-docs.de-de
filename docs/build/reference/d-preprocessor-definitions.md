---
title: /D (Präprozessordefinitionen)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.PreprocessorDefinitions
- VC.Project.VCCLCompilerTool.PreprocessorDefinitions
- /d
helpviewer_keywords:
- preprocessor definition symbols
- constants, defining
- macros, compiling
- /D compiler option [C++]
- -D compiler option [C++]
- D compiler option [C++]
ms.assetid: b53fdda7-8da1-474f-8811-ba7cdcc66dba
ms.openlocfilehash: 089f34f6daa606ed2869852a04ee76c6bda8fe25
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424677"
---
# <a name="d-preprocessor-definitions"></a>/D (Präprozessordefinitionen)

Definiert ein Vorverarbeitungssymbol für eine Quelldatei.

## <a name="syntax"></a>Syntax

```
/Dname[= | # [{string | number}] ]
```

## <a name="remarks"></a>Hinweise

Sie können dieses Symbol mit `#if` oder `#ifdef` zur bedingten Kompilierung von Quellcode verwenden. Die Symboldefinition bleibt bestehen, bis sie im Code neu definiert wird oder ihre Definition im Code durch die `#undef`-Direktive aufgehoben wird.

**/ D** hat dieselbe Wirkung wie das `#define` -Direktive am Anfang einer Quellcodedatei, außer dass **/d** Anführungszeichen in der Befehlszeile entfernt und `#define` beibehält.

Standardmäßig wird einem Symbol der Wert 1 zugeordnet. Z. B. **/d** `name` entspricht **/d**`name`**= 1**. Im Beispiel am Ende dieses Artikels die Definition der **TEST** wird angezeigt, um Drucken `1`.

Kompilieren mithilfe von **/d** `name` **=** wird dem Symbol kein Wert zugeordnet. Obwohl das Symbol trotzdem zur bedingten Codekompilierung verwendet werden kann, ergibt das Symbol keinen Wert. Im Beispiel, wenn Sie bei der Kompilierung **/DTEST =**, ein Fehler auftritt. Dieses Verhalten ähnelt der Verwendung von `#define` mit oder ohne Wert.

Dieser Befehl definiert das DEBUG-Symbol in TEST.C:

**CL DDEBUG TESTEN. C**

Mit dem folgenden Befehl werden alle Vorkommen des Schlüsselworts `__far` aus TEST.C entfernt.

**CL-/D__far = TEST. C**

Die **CL** Umgebungsvariable kann nicht festgelegt werden, um eine Zeichenfolge mit dem Gleichheitszeichen. Verwendung von **/d** zusammen mit den **CL** Umgebung Variablen, Sie müssen angeben, die Nummernzeichen anstelle eines Gleichheitszeichens:

```
SET CL=/DTEST#0
```

Wenn Sie ein Vorverarbeitungssymbol an der Eingabeaufforderung definieren, sollten Sie Compileranalyseregeln sowie Shell-Analyseregeln berücksichtigen. Beispielsweise definiert ein Vorverarbeitungssymbol Prozentzeichen (%) Geben Sie in Ihrem Programm zwei Prozentzeichen (%) an der Eingabeaufforderung: Wenn Sie nur eine angeben, wird ein Analysefehler ausgegeben.

```
CL /DTEST=%% TEST.C
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie im linken Bereich **Konfigurationseigenschaften**, **C/C++-**, **Präprozessor**.

1. Im rechten Bereich, in der rechten Spalte von der **Präprozessordefinitionen** Eigenschaft öffnen Sie das Dropdown-Menü, und wählen Sie **bearbeiten**.

1. In der **Präprozessordefinitionen** Dialogfeld (eines pro Zeile) hinzufügen, ändern oder löschen Sie eine oder mehrere Definitionen. Klicken Sie auf **OK**, um die Änderungen zu speichern.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PreprocessorDefinitions%2A>.

## <a name="example"></a>Beispiel

```
// cpp_D_compiler_option.cpp
// compile with: /DTEST
#include <stdio.h>

int main( )
{
    #ifdef TEST
        printf_s("TEST defined %d\n", TEST);
    #else
        printf_s("TEST not defined\n");
    #endif
}
```

```Output
TEST defined 1
```

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[/U, /u (Symboldefinitionen aufheben)](../../build/reference/u-u-undefine-symbols.md)<br/>
[#undef-Direktive (C/C++)](../../preprocessor/hash-undef-directive-c-cpp.md)<br/>
[#define-Direktive (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)
