---
title: "/GL (Optimierung des ganzen Programms)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "/gl"
  - "VC.Project.VCCLWCECompilerTool.WholeProgramOptimization"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GL (Compileroption) [C++]"
  - "GL (Compileroption) [C++]"
  - "-GL (Compileroption) [C++]"
  - "Optimierungen ganzer Programme und C++-Compiler"
ms.assetid: 09d51e2d-9728-4bd0-b5dc-3b8284aca1d1
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# /GL (Optimierung des ganzen Programms)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aktiviert die Optimierung des gesamten Programms.  
  
## Syntax  
  
```  
/GL[-]  
```  
  
## Hinweise  
 Durch die Optimierung des ganzen Programms kann der Compiler Optimierungen mit Informationen zu allen Modulen im Programm durchführen.  Ohne diese Option werden Optimierungen auf Modulbasis durchgeführt.  
  
 Standardmäßig ist die Optimierung des ganzen Programms deaktiviert, d. h., sie muss ausdrücklich aktiviert werden.  Sie kann jedoch mit **\/GL\-** auch explizit deaktiviert werden.  
  
 Mit Informationen zu allen Modulen kann der Compiler  
  
-   den funktionsübergreifenden Gebrauch von Registern optimieren;  
  
-   Änderungen globaler Daten besser verfolgen, sodass die Anzahl der Lade\- und Speichervorgänge verringert werden kann;  
  
-   den möglichen durch einen Zeigerverweis geänderten Satz von Elementen besser verfolgen und die Anzahl der Lade\- und Speichervorgänge verringern;  
  
-   eine Funktion in einem Modul inline erweitern, auch wenn diese Funktion in einem anderen Modul definiert ist.  
  
 Mit **\/GL** erstellte OBJ\-Dateien stehen Linkerdienstprogrammen wie [EDITBIN](../../build/reference/editbin-reference.md) und [DUMPBIN](../../build/reference/dumpbin-reference.md) nicht zur Verfügung.  
  
 Wenn Sie das Programm mit **\/GL** und [\/c](../../build/reference/c-compile-without-linking.md) kompilieren, sollten Sie zum Erstellen der Ausgabedatei die \/LTCG\-Linkeroption verwenden.  
  
 [\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) kann nicht mit **\/GL** verwendet werden.  
  
 Das Format der mit **\/GL** in der aktuellen Version erstellten Dateien kann möglicherweise von Folgeversionen von Visual C\+\+ nicht mehr gelesen werden.  Sie sollten nur dann eine aus mit **\/GL** erstellten OBJ\-Dateien bestehende LIB\-Datei verteilen, wenn Sie eine Verteilung der LIB\-Datei für alle Versionen von Visual C\+\+ planen, die die Benutzer jetzt und in Zukunft verwenden.  
  
 Mit **\/GL** erstellte OBJ\-Dateien und vorkompilierte Headerdateien sollten nur dann zur Erstellung einer LIB\-Datei verwendet werden, wenn die LIB\-Datei auf demselben Computer verknüpft wird, auf dem die OBJ\-Datei mit **\/GL** erstellt wurde.  Beim Verknüpfen werden Informationen aus der vorkompilierten Headerdatei der OBJ\-Datei benötigt.  
  
 Weitere Informationen über die Optimierungen, die mit verfügbaren und die Einschränkungen der ganzen Programmoptimierung, finden Sie unter [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md). **\/GL** stellt außerdem profilgesteuerte Optimierung \(PGO\) bereit; finden Sie \/LTCG.  Wenn Sie für profilgesteuerte Optimierungen kompilieren und dabei die Funktionsanordnung nutzen möchten, müssen Sie mit [\/Gy](../../build/reference/gy-enable-function-level-linking.md) oder einer Compileroption kompilieren, die "\/Gy" impliziert.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Weitere Informationen zum Festlegen von **\/GL** in der Entwicklungsumgebung finden Sie unter [\/LTCG \(Code zur Verknüpfungszeit generieren\)](../../build/reference/ltcg-link-time-code-generation.md).  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)