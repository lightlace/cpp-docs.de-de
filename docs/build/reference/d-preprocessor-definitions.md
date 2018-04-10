---
title: -D (Präprozessordefinitionen) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCNMakeTool.PreprocessorDefinitions
- VC.Project.VCCLCompilerTool.PreprocessorDefinitions
- /d
dev_langs:
- C++
helpviewer_keywords:
- preprocessor definition symbols
- constants, defining
- macros, compiling
- /D compiler option [C++]
- -D compiler option [C++]
- D compiler option [C++]
ms.assetid: b53fdda7-8da1-474f-8811-ba7cdcc66dba
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 08812cdd0a4ffb27b387cce8cfb26e72ef80770a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
  
 Standardmäßig wird einem Symbol der Wert 1 zugeordnet. Beispielsweise **/d** `name` entspricht **/d**`name`**= 1**. Im Beispiel am Ende dieses Artikels, die Definition der **TEST** wird angezeigt, die Drucken `1`.  
  
 Eine Kompilierung mit **/d** `name`  **=**  wird dem Symbol kein Wert zugeordnet. Obwohl das Symbol trotzdem zur bedingten Codekompilierung verwendet werden kann, ergibt das Symbol keinen Wert. Im Beispiel, wenn Sie bei der Kompilierung **/DTEST =**, ein Fehler auftritt. Dieses Verhalten ähnelt der Verwendung von `#define` mit oder ohne Wert.  
  
 Dieser Befehl definiert das DEBUG-Symbol in TEST.C:  
  
 **CL DDEBUG TEST. C**  
  
 Mit dem folgenden Befehl werden alle Vorkommen des Schlüsselworts `__far` aus TEST.C entfernt.  
  
 **CL-/D__far = TEST. C**  
  
 Die **CL** -Umgebungsvariable kann nicht festgelegt werden, um eine Zeichenfolge, die das Gleichheitszeichen enthält. Mit **/d** zusammen mit den **CL** Umgebung-Variable verwenden, müssen die Nummernzeichen anstelle eines Gleichheitszeichens angeben:  
  
```  
SET CL=/DTEST#0  
```  
  
 Wenn Sie ein Vorverarbeitungssymbol an der Eingabeaufforderung definieren, sollten Sie Compileranalyseregeln sowie Shell-Analyseregeln berücksichtigen. Wenn Sie beispielsweise im Programm ein Vorverarbeitungssymbol für ein Prozentzeichen (%) definieren möchten, geben Sie an der Eingabeaufforderung zwei Prozentzeichen (%%) ein: Bei Angabe von nur einem Zeichen wird ein Analysefehler ausgegeben.  
  
```  
CL /DTEST=%% TEST.C  
```  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie im linken Bereich **Konfigurationseigenschaften**, **C/C++-**, **Präprozessor**.  
  
3.  Im rechten Bereich, in der rechten Spalte von der **Präprozessordefinitionen** -Eigenschaft, öffnen Sie das Dropdownmenü, und wählen Sie **bearbeiten**.  
  
4.  In der **Präprozessordefinitionen** (Dialogfeld), (eines pro Zeile) hinzufügen, ändern oder löschen Sie eine oder mehrere Definitionen. Wählen Sie **OK** zum Speichern der Änderungen.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PreprocessorDefinitions%2A>.  
  
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
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [/ U, / u (Symboldefinitionen aufheben)](../../build/reference/u-u-undefine-symbols.md)   
 [#undef-Direktive (C/C++)](../../preprocessor/hash-undef-directive-c-cpp.md)   
 [#define-Direktive (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)