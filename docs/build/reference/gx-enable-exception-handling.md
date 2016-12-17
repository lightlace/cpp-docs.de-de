---
title: "/GX (Ausnahmebehandlung aktivieren)"
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
  - "/gx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GX (Compileroption) [C++]"
  - "cl.exe-Compiler, Ausnahmebehandlung"
  - "Aktivieren der Ausnahmebehandlung (Compileroption) [C++]"
  - "Ausnahmebehandlung, Aktivieren"
  - "GX (Compileroption) [C++]"
  - "-GX (Compileroption) [C++]"
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
caps.latest.revision: 16
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# /GX (Ausnahmebehandlung aktivieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Option ermöglicht die synchrone Ausnahmebehandlung mit der Annahme, dass `extern` C\-Funktionen keine Ausnahme verursachen.  
  
## Syntax  
  
```  
/GX  
```  
  
## Hinweise  
 Ist äquivalent zu [\/EH \(Ausnahmebehandlungsmodell\)](../../build/reference/eh-exception-handling-model.md).  
  
 **\/GX** ist standardmäßig aktiviert, wenn Sie aus der Entwicklungsumgebung kompilieren.  **\/GX\-** ist standardmäßig aktiviert, wenn Sie Befehlszeilentools verwenden.  
  
 Weitere Informationen finden Sie unter [C\+\+\-Ausnahmebehandlung](../../cpp/cpp-exception-handling.md).  
  
 **\/GX** ist veraltet. Verwenden Sie stattdessen [\/EH \(Ausnahmebehandlungsmodell\)](../../build/reference/eh-exception-handling-model.md).  Weitere Informationen finden Sie unter [Deprecated Compiler Options in Visual C\+\+ 2005](assetId:///aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
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