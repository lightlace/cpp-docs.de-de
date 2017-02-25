---
title: "/X (Standardincludepfade ignorieren) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/x"
  - "VC.Project.VCCLCompilerTool.IgnoreStandardIncludePath"
  - "VC.Project.VCCLWCECompilerTool.IgnoreStandardIncludePath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/X (Compileroption) [C++]"
  - "Standardincludepfad ignorieren (Compileroption)"
  - "Includeverzeichnisse, Standard ignorieren"
  - "Includedateien, Standardpfad ignorieren"
  - "X (Compileroption)"
  - "-X (Compileroption) [C++]"
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /X (Standardincludepfade ignorieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Hindert den Compiler daran, in den Verzeichnissen, die in den Umgebungsvariablen PATH und INCLUDE angegeben sind, nach Includedateien zu suchen.  
  
## Syntax  
  
```  
/X  
```  
  
## Hinweise  
 Sie können diese Option zusammen mit der [\/I \(Zusätzliche Includeverzeichnisse\)](../../build/reference/i-additional-include-directories.md)\-Option \(**\/I**`directory`\) verwenden.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Präprozessor**.  
  
4.  Ändern Sie die Eigenschaft **Standardincludepfad ignorieren**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath*>.  
  
## Beispiel  
 Im folgenden Befehl weist `/X` den Compiler an, von den Umgebungsvariablen **PATH** und **INCLUDE** festgelegte Speicherorte zu ignorieren, und `/I` gibt das Verzeichnis an, in dem nach Includedateien gesucht werden soll:  
  
```  
CL /X /I \ALT\INCLUDE MAIN.C  
```  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)