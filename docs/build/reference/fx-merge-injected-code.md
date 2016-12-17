---
title: "/Fx (Eingef&#252;gten Code zusammenf&#252;hren)"
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
  - "VC.Project.VCCLWCECompilerTool.ExpandAttributedSource"
  - "/Fx"
  - "VC.Project.VCCLCompilerTool.ExpandAttributedSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fx (Compileroption) [C++]"
  - "-Fx (Compileroption) [C++]"
  - "Eingefügter Code"
  - "Zusammenführen von eingefügtem Code"
  - "/Fx (Compileroption) [C++]"
ms.assetid: 14f0e301-3bab-45a3-bbdf-e7ce66f20560
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# /Fx (Eingef&#252;gten Code zusammenf&#252;hren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erzeugt eine Kopie jeder Quelldatei mit injiziertem Code, der in die Quelle eingefügt ist.  
  
## Syntax  
  
```  
/Fx  
```  
  
## Hinweise  
 Damit eine zusammengeführte Quelldatei von einer unveränderten Quelldatei unterschieden werden kann, fügt **\/Fx** die Erweiterung „.mrg“ zwischen dem Dateinamen und der Dateierweiterung ein. Eine Datei mit dem Namen „MeinCode.cpp“, die attribuierten Code enthält und mit **\/Fx** erstellt wird, erzeugt eine Datei mit dem Namen „MyCode.mrg.cpp“, die den folgenden Code enthält:  
  
```  
//+++ Start Injected Code [no_injected_text(true)];      // Suppress injected text, it has // already been injected #pragma warning(disable: 4543) // Suppress warnings about skipping // injected text #pragma warning(disable: 4199) // Suppress warnings from attribute // providers //--- End Injected Code  
```  
  
 In einer MRG\-Datei wird Code, der aufgrund eines Attributs injiziert wurde, wie folgt abgetrennt:  
  
```  
//+++ Start Injected Code ... //--- End Injected Code  
```  
  
 Das [no\_injected\_text](../../windows/no-injected-text.md)\-Attribut wird in eine MRG\-Datei eingebettet, was die Kompilierung der MRG\-Datei ohne erneute Injizierung von Text ermöglicht.  
  
 Es sollte Ihnen bewusst sein, dass die MRG\-Quelldatei als Darstellung des vom Compiler injizierten Quellcodes beabsichtigt ist. Die MRG\-Datei lässt sich möglicherweise nicht genau wie die ursprüngliche Quelldatei kompilieren oder ausführen.  
  
 Makros werden in der MRG\-Datei nicht erweitert.  
  
 Wenn Ihr Programm eine Headerdatei umfasst, die injizierten Code verwendet, erstellt **\/Fx** eine „.mrg.h“\-Datei für den betreffenden header.**\/Fx** führt keine Includedateien zusammen, die keinen injizierten Code verwenden.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken  Sie auf die Eigenschaftenseite **Ausgabedateien**.  
  
4.  Ändern Sie die **Expand Attributed Source**\-Eigenschaft.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExpandAttributedSource*>.  
  
## Siehe auch  
 [\/F\-Optionen \(Ausgabedateioptionen\)](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)