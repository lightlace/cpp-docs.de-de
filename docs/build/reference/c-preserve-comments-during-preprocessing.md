---
title: "/C (Kommentare bei der Vorverarbeitung beibehalten) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.KeepComments"
  - "/c"
  - "VC.Project.VCCLWCECompilerTool.KeepComments"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/c (Compileroption) [C++]"
  - "c (Compileroption) [C++]"
  - "-c (Compileroption) [C++]"
  - "Kommentare, Beim Vorverarbeiten nicht entfernen"
  - "Beibehalten von Kommentaren beim Vorverarbeiten"
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /C (Kommentare bei der Vorverarbeitung beibehalten)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Behält Kommentare beim Präprozessorlauf bei  
  
## Syntax  
  
```  
/C  
```  
  
## Hinweise  
 Diese Compileroption erfordert eine der Optionen **\/E**, **\/P** oder **\/EP**.  
  
 Im folgenden Codebeispiel wird der Quellcodekommentar angezeigt.  
  
```  
// C_compiler_option.cpp  
// compile with: /E /C /c  
int i;   // a variable  
```  
  
 In diesem Beispiel wird die folgende Ausgabe generiert.  
  
```  
#line 1 "C_compiler_option.cpp"  
int i;   // a variable  
```  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Präprozessor**.  
  
4.  Ändern Sie die Eigenschaft **Kommentare beibehalten**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [\/E \(Vorverarbeitung an "stdout"\)](../../build/reference/e-preprocess-to-stdout.md)   
 [\/P \(Vorverarbeitung in eine Datei\)](../../build/reference/p-preprocess-to-a-file.md)   
 [\/EP \(Vorverarbeitung an "stdout" ohne \#line\-Direktiven\)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)