---
title: "/showIncludes (Includedateien auflisten) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.ShowIncludes"
  - "VC.Project.VCCLCompilerTool.ShowIncludes"
  - "/showincludes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/showIncludes (Compileroption) [C++]"
  - "Includedateien"
  - "Includedateien, Anzeigen in Kompilierung"
  - "showIncludes (Compileroption) [C++]"
  - "-showIncludes (Compileroption) [C++]"
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /showIncludes (Includedateien auflisten)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Veranlasst den Compiler, eine Liste der Includedateien auszugeben.  Auch geschachtelte Includedateien werden angezeigt \(Dateien, die die hinzugefügten Dateien selbst hinzufügen\).  
  
## Syntax  
  
```  
/showIncludes  
```  
  
## Hinweise  
 Trifft der Compiler auf eine Includedatei, wird eine Meldung wie die Folgende angezeigt:  
  
```  
Note: including file: d:\MyDir\include\stdio.h  
```  
  
 Geschachtelte Includedateien werden durch Einzug kenntlich gemacht. Ein Leerzeichen steht dabei für jeweils eine Schachtelungsebene. Beispiel:  
  
```  
Note: including file: d:\temp\1.h  
Note: including file:  d:\temp\2.h  
```  
  
 In diesem Fall wurde innerhalb von `1.h` auf `2.h` verwiesen und die Zeile daher eingerückt.  
  
 Die **\/showIncludes**\-Option gibt in `stderr` aus, nicht in `stdout`.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **Includes anzeigen**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)