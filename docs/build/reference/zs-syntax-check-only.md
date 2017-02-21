---
title: "/Zs (Nur Syntax&#252;berpr&#252;fung) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/zs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zs (Compileroption) [C++]"
  - "Nur Syntaxüberprüfung (Compileroption)"
  - "Zs (Compileroption)"
  - "-Zs (Compileroption) [C++]"
ms.assetid: b4b41e6a-3f41-4d09-9cb6-fde5aa2cfecf
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /Zs (Nur Syntax&#252;berpr&#252;fung)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Option weist den Compiler an, nur die Syntax der Quelldateien in der Befehlszeile zu prüfen.  
  
## Syntax  
  
```  
/Zs  
```  
  
## Hinweise  
 Wenn Sie diese Option verwenden, werden keine Ausgabedateien erstellt, und Fehlermeldungen werden in die Standardausgabe geschrieben.  
  
 Die Option **\/Zs** ermöglicht eine schnelle Suche und Korrektur von Syntaxfehlern vor dem Kompilieren und Verknüpfen einer Quelldatei.  
  
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