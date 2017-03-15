---
title: "/FI (Name der expliziten Includedatei) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCNMakeTool.ForcedIncludes"
  - "VC.Project.VCCLCompilerTool.ForcedIncludeFiles"
  - "VC.Project.VCCLWCECompilerTool.ForcedIncludeFiles"
  - "/fi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FI (Compileroption) [C++]"
  - "FI (Compileroption) [C++]"
  - "-FI (Compileroption) [C++]"
  - "Vorverarbeiten einer Headerdatei (Compileroption) [C++]"
ms.assetid: 07e79577-8152-4df9-a64c-aae08c603397
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /FI (Name der expliziten Includedatei)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Option weist den Präprozessor an, die angegebene Headerdatei zu verarbeiten.  
  
## Syntax  
  
```  
/FI[ ]pathname  
```  
  
## Hinweise  
 Diese Option hat dieselben Auswirkungen, als sei die Datei mit doppelten Anführungszeichen in einer \#include\-Direktive in der ersten Zeile jeder Quelldatei angegeben, die in der Befehlszeile, in der Umgebungsvariablen **CL** oder in einer Befehlsdatei angeführt wird.  Bei Verwendung mehrerer **\/FI**\-Optionen werden die Dateien in der Reihenfolge einbezogen, in der sie von CL verarbeitet werden.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **Includes erzwingen**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles*>.  
  
## Siehe auch  
 [\/F\-Optionen \(Ausgabedateioptionen\)](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)