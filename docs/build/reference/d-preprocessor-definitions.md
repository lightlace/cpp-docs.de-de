---
title: "/D (Pr&#228;prozessordefinitionen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCNMakeTool.PreprocessorDefinitions"
  - "VC.Project.VCCLCompilerTool.PreprocessorDefinitions"
  - "/d"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/D (Compileroption) [C++]"
  - "Konstanten, Definieren"
  - "D (Compileroption) [C++]"
  - "-D (Compileroption) [C++]"
  - "Makros, Kompilieren"
  - "Präprozessordefinitionssymbole"
ms.assetid: b53fdda7-8da1-474f-8811-ba7cdcc66dba
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# /D (Pr&#228;prozessordefinitionen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Definiert ein Vorverarbeitungssymbol für eine Quelldatei.  
  
## Syntax  
  
```  
/Dname[= | # [{string | number}] ]  
```  
  
## Hinweise  
 Sie können dieses Symbol mit `#if` oder `#ifdef` zur bedingten Kompilierung von Quellcode verwenden.  Die Symboldefinition bleibt bestehen, bis sie im Code neu definiert wird oder ihre Definition im Code durch die `#undef`\-Direktive aufgehoben wird.  
  
 **\/D** erzielt denselben Effekt wie die `#define`\-Direktive am Anfang einer Quellcodedatei, wobei jedoch **\/D** die Anführungszeichen in der Befehlszeile entfernt und `#define` sie beibehält.  
  
 Standardmäßig wird einem Symbol der Wert 1 zugeordnet.  **\/D**`name` entspricht beispielsweise **\/D**`name`**\=1**.  In dem Beispiel am Ende dieses Artikels wird dargestellt, wie bei der Definition von **TEST** der Wert `1` ausgegeben wird.  
  
 Beim Kompilieren mithilfe von **\/D**`name`**\=** wird dem Symbol kein Wert zugeordnet.  Obwohl das Symbol trotzdem zur bedingten Codekompilierung verwendet werden kann, ergibt das Symbol keinen Wert.  Wenn Sie zum Beispiel mithilfe von **\/DTEST\=** kompilieren, tritt ein Fehler auf.  Dieses Verhalten ähnelt der Verwendung von `#define` mit oder ohne Wert.  
  
 Dieser Befehl definiert das DEBUG\-Symbol in TEST.C:  
  
 **CL \/DDEBUG  TEST.C**  
  
 Mit dem folgenden Befehl werden alle Vorkommen des Schlüsselworts `__far` aus TEST.C entfernt.  
  
 **CL \/D\_\_far\=  TEST.C**  
  
 Sie können die Umgebungsvariable **CL** nicht für eine Zeichenfolge festlegen, die ein Gleichheitszeichen enthält.  Wenn Sie **\/D** zusammen mit der Umgebungsvariablen **CL** verwenden möchten, geben Sie ein Nummernzeichen anstelle eines Gleichheitszeichens an.  
  
```  
SET CL=/DTEST#0  
```  
  
 Wenn Sie ein Vorverarbeitungssymbol an der Eingabeaufforderung definieren, sollten Sie Compileranalyseregeln sowie Shell\-Analyseregeln berücksichtigen.  Wenn Sie beispielsweise im Programm ein Vorverarbeitungssymbol für ein Prozentzeichen \(%\) definieren möchten, geben Sie an der Eingabeaufforderung zwei Prozentzeichen \(%%\) ein: Bei Angabe von nur einem Zeichen wird ein Analysefehler ausgegeben.  
  
```  
CL /DTEST=%% TEST.C  
```  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Wählen Sie im linken Bereich die Optionen **Konfigurationseigenschaften**, **C\/C\+\+**, **Präprozessor** aus.  
  
3.  Wählen Sie im rechten Bereich in der rechten Spalte der Eigenschaft **Präprozessordefinitionen** im Dropdownmenü die Option **Bearbeiten** aus.  
  
4.  Gehen Sie im Dialogfeld **Präprozessordefinitionen** folgendermaßen vor: Fügen Sie \(zeilenweise\) eine oder mehrere Definitionen hinzu bzw. ändern oder löschen Sie eine oder mehrere Definitionen.  Klicken Sie auf **OK**, um die Änderungen zu speichern.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PreprocessorDefinitions*>.  
  
## Beispiel  
  
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
  
  **TEST definiert 1**   
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [\/U, \/u \(Symboldefinitionen aufheben\)](../../build/reference/u-u-undefine-symbols.md)   
 [\#undef\-Direktive](../../preprocessor/hash-undef-directive-c-cpp.md)   
 [\#define\-Direktive](../../preprocessor/hash-define-directive-c-cpp.md)