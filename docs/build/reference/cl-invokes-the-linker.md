---
title: "CL: Starten des Linkers"
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
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler [C++], Kompilieren ohne Verknüpfen"
  - "cl.exe-Compiler [C++], Steuern des Linkers"
  - "Kompilieren von Quellcode [C++], Ohne Verknüpfen"
  - "Aufrufen des Linkers aus dem Compiler"
  - "LINK-Tool [C++], Aufrufen aus dem CL-Compiler"
ms.assetid: eae47ef7-09eb-40c9-b318-7c714cd452fc
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# CL: Starten des Linkers
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CL startet den Linker automatisch nach dem Kompilieren, sofern nicht die \/c\-Option verwendet wird.  CL übergibt dem Linker die Namen der OBJ\-Dateien, die während des Kompilierens erstellt wurden, und die Namen aller anderen in der Befehlszeile angegebenen Dateien.  Der Linker verwendet die Optionen, die in der Umgebungsvariablen **LINK** aufgeführt sind.  Mit der \/link\-Option können in der CL\-Befehlszeile Optionen für den Linker angegeben werden.  Optionen, die der \/link\-Option folgen, überschreiben die Optionen in der Umgebungsvariablen **LINK**.  Die Optionen in der nachfolgenden Tabelle unterdrücken das Verknüpfen.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|\/c|Kompilieren ohne Verknüpfen|  
|\/E, \/EP, \/P|Vorverarbeiten ohne Kompilieren und Verknüpfen|  
|\/Zg|Funktionsprototypen generieren|  
|\/Zs|Syntax prüfen|  
  
 Weitere Details zum Verknüpfen finden Sie im Abschnitt [Linkeroptionen](../../build/reference/linker-options.md).  
  
## Beispiel  
 Angenommen, Sie kompilieren drei C\-Quelldateien: MAIN.c, MOD1.c, and MOD2.c.  Jede Datei enthält einen Aufruf einer in einer anderen Datei definierten Funktion:  
  
-   **MAIN.c** ruft die Funktion `func1` in **MOD1.c** und die Funktion `func2` in **MOD2.c** auf.  
  
-   MOD1.c ruft die Standardbibliotheksfunktionen `printf_s` und `scanf_s` auf.  
  
-   **MOD2.c** ruft die Grafikfunktionen `myline` und `mycircle` auf, die in der Bibliothek **MYGRAPH.lib** definiert sind.  
  
 Zum Erstellen dieses Programms kompilieren Sie mit folgender Befehlszeile:  
  
```  
CL MAIN.c MOD1.C MOD2.C MYGRAPH.lib  
```  
  
 CL kompiliert zunächst die C\-Quelldateien und erstellt die Objektdateien **MAIN.obj**, **MOD1.obj** und **MOD2.obj**.  Der Compiler legt den Namen der Standardbibliothek in jeder OBJ\-Datei ab.  Näheres dazu finden Sie unter [Laufzeitbibliothek verwenden](../../build/reference/md-mt-ld-use-run-time-library.md).  
  
 CL übergibt die Namen der OBJ\-Dateien zusammen mit dem Namen **MYGRAPH.lib** an den Linker.  Der Linker löst die externen Verweise folgendermaßen auf:  
  
1.  In **MAIN.obj** wird der Verweis auf `func1` mit der Definition aus **MOD1.obj** und der Verweis auf `func2` mit der Definition aus **MOD2.obj** aufgelöst.  
  
2.  In MOD1.obj werden die Verweise auf `printf_s` und `scanf_s` mit den Definitionen in der Bibliothek aufgelöst, deren Namen der Linker in MOD1.obj vorfindet.  
  
3.  In **MOD2.obj** werden die Verweise auf `myline` und `mycircle` mit den Definitionen aus **MYGRAPH.lib** aufgelöst.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)