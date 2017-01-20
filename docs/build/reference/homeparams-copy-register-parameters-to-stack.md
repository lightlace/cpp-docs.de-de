---
title: "/homeparams (Registerparameter in den Stapel kopieren)"
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
  - "/homeparams"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/homeparams (Compileroption) [C++]"
  - "-homeparams (Compileroption) [C++]"
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# /homeparams (Registerparameter in den Stapel kopieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erzwingt, dass in Registern übergebene Parameter bei Funktionseinstieg in ihre Speicherorte auf dem Stapel geschrieben werden.  
  
## Syntax  
  
```  
/homeparams  
```  
  
## Hinweise  
 Diese Compileroption gilt nur für die [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\-Compiler \(systemeigene und Cross\-Compiler\).  
  
 Wenn in einer [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\-Kompilierung Parameter übergeben werden, ist für Aufrufkonventionen Stapelspeicher für Parameter erforderlich. Dies gilt auch für Parameter, die in Registern übergeben werden.  Weitere Informationen finden Sie unter [Parameterübergabe](../../build/parameter-passing.md).  In der Standardeinstellung werden in einem Releasebuild die Registerparameter jedoch nicht in den Stapelspeicher geschrieben, der bereits für die Parameter zur Verfügung gestellt wird.  Dadurch ergeben sich Schwierigkeiten beim Debuggen eines optimierten \(Release\-\)Builds des Programms.  
  
 Verwenden Sie für einen Releasebuild **\/homeparams**, um sicherzustellen, dass Sie in der Lage sind, die Anwendung zu debuggen.  **\/homeparams** führt zu einer verminderten Leistung, da für das Laden der Registerparameter auf den Stapel ein Zyklus erforderlich ist.  
  
 In einem Debugbuild wird der Stapel stets mit Parametern ausgefüllt, die in Registern übergeben werden.  
  
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