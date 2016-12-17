---
title: "/CGTHREADS (Compilerthreads)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CGTHREADS-Linkeroption"
  - "CGTHREADS-Linkeroption"
  - "-CGTHREADS-Linkeroption"
ms.assetid: 4b52cfdb-3702-470b-9580-fabeb1417488
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# /CGTHREADS (Compilerthreads)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt die Anzahl von cl.exe\-Threads zur Verwendung für die Optimierung und Codegenerierung fest, wenn die Link\-Zeitcodegenerierung angegeben ist.  
  
## Syntax  
  
```  
/CGTHREADS:[1-8]  
```  
  
## Argumente  
 number  
 Die maximale Anzahl von Threads zur Verwendung für cl.exe, im Bereich von 1 bis 8.  
  
## Hinweise  
 Die Option **\/CGTHREADS** gibt die maximale Anzahl von Threads an, die cl.exe parallel für die Optimierungs\- und Codegenerierungsphase der Kompilierung verwendet, wenn die Link\-Zeitcodegenerierung \([\/LTCG](../../build/reference/ltcg-link-time-code-generation.md)\) angegeben ist.  Standardmäßig verwendet cl.exe vier Threads, als wäre **\/CGTHREADS:4** angegeben.  Wenn mehr Prozessorkerne verfügbar sind, kann ein höherer `number`\-Wert die Builderstellung beschleunigen.  
  
 Für einen Build können mehrere Stufen der Parallelität angegeben werden.  Der msbuild.exe\-Switch **\/maxcpucount** gibt die Anzahl der MSBuild\-Prozesse an, die parallel ausgeführt werden können.  Das [\/MP \(Erstellen mit mehreren Prozessen\)](../../build/reference/mp-build-with-multiple-processes.md)\-Compilerflag gibt die Anzahl der cl.exe\-Prozesse an, die gleichzeitig die Quelldateien kompilieren.  Die Compileroption [\/cgthreads](../../build/reference/cgthreads-code-generation-threads.md) gibt die Anzahl von Threads an, die von jedem cl.exe\-Prozess verwendet werden.  Da der Prozessor nur so viele Threads gleichzeitig ausführen kann, wie Prozessorkerne vorhanden sind, ist es nicht sinnvoll, größere Werte für all diese Optionen gleichzeitig anzugeben. Das kann sogar kontraproduktiv sein.  Weitere Informationen zum parallelen Erstellen von Projekten finden Sie unter [Building Multiple Projects in Parallel](../Topic/Building%20Multiple%20Projects%20in%20Parallel%20with%20MSBuild.md).  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **Konfigurationseigenschaften**, **Linker** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Ändern Sie die Eigenschaft **Zusätzliche Optionen** so, dass **\/CGTHREADS:**`number` eingeschlossen ist, wobei `number` ein Wert von 1 bis 8 ist, und wählen Sie dann **OK** aus.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Linkeroptionen](../../build/reference/linker-options.md)   
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)