---
title: "/Y- (Vorkompilierte Headeroptionen ignorieren) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/y-"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Y- (Compileroption) [C++]"
  - "-Y- (Compileroption) [C++]"
  - "Y- (Compileroption) [C++]"
ms.assetid: cfaecb36-58db-46b8-b04d-cca6072b1b7a
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /Y- (Vorkompilierte Headeroptionen ignorieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bewirkt, dass alle anderen `/Y`\-Compileroptionen ignoriert werden \(und kann selbst nicht überschrieben werden\).  
  
## Syntax  
  
```  
/Y-  
```  
  
## Hinweise  
 Weitere Informationen zu vorkompilierten Headern finden Sie unter:  
  
-   [\/Y \(Vorkompilierte Header\)](../../build/reference/y-precompiled-headers.md)  
  
-   [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)  
  
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