---
title: "/GA (F&#252;r Windows-Anwendung optimieren) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication"
  - "/ga"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GA (Compileroption) [C++]"
  - "GA (Compileroption) [C++]"
  - "-GA (Compileroption) [C++]"
  - "Optimieren für Windows (Compileroptionen)"
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /GA (F&#252;r Windows-Anwendung optimieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt bei einer EXE\-Datei zur Erzeugung effizienteren Codes für den Zugriff auf Variablen des lokalen Threadspeichers \(TLS\).  
  
## Syntax  
  
```  
/GA  
```  
  
## Hinweise  
 **\/GA** beschleunigt den Zugriff auf Daten, die in einem Windows\-basierten Programm als [\_\_declspec\(thread\)](../../cpp/declspec.md) deklariert sind.  Wenn diese Option aktiviert ist, wird angenommen, dass das Makro [\_\_tls\_index](http://msdn.microsoft.com/library/windows/desktop/ms686749) den Wert 0 hat.  
  
 Die Verwendung von **\/GA** für eine DLL kann zur Generierung von ungültigem Code führen.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)