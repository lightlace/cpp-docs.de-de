---
title: "/hotpatch (Erstellen eines Hotpatch-f&#228;higen Abbildes) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/hotpatch"
  - "VC.Project.VCCLCompilerTool.CreateHotpatchableImage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Hotpatching"
  - "-hotpatch (Compileroption) [C++]"
  - "/hotpatch (Compileroption) [C++]"
  - "hotpatch"
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# /hotpatch (Erstellen eines Hotpatch-f&#228;higen Abbildes)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bereitet ein Image für Hotpatching vor.  
  
## Syntax  
  
```  
/hotpatch  
```  
  
## Hinweise  
 Wenn für eine Kompilierung **\/hotpatch** verwendet wird, wird durch den Compiler sichergestellt, dass die erste Anweisung jeder Funktion mindestens über die für das Hotpatching erforderliche Größe von zwei Bytes verfügt.  
  
 Zum Abschließen der Vorbereitung von einem Image, damit es hotpatchfähig wird, müssen Sie nach der Verwendung von **\/hotpatch** mit [\/FUNCTIONPADMIN \(Erstellen eines Hotpatch\-fähigen Abbildes\)](../../build/reference/functionpadmin-create-hotpatchable-image.md) einen Link erstellen.  Wenn Sie zum Kompilieren und Verknüpfen von einem Image einen einzelnen Aufruf von CL.EXE verwenden, impliziert **\/hotpatch** die Option **\/functionpadmin**.  
  
 Da Befehle in der ARM\-Architektur immer zwei Bytes oder mehr umfassen und die x64\-Kompilierung immer so ausgeführt wird, als wäre **\/hotpatch** festgelegt, müssen Sie **\/hotpatch** nicht angeben, wenn Sie für diese Ziele kompilieren. Sie müssen jedoch weiterhin mithilfe von **\/functionpadmin** linken, um hotpatchfähige Images für diese Ziele zu erstellen.  Die **\/hotpatch**\-Compileroption beeinflusst nur die x86\-Kompilierung.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Wählen Sie den Ordner **C\/C\+\+** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Fügen Sie die Compileroption dem Feld **Zusätzliche Optionen** hinzu.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Empfehlungen  
 Weitere Informationen über die Updateverwaltung finden Sie im Leitfaden zur Sicherheit für die Updateverwaltung unter [http:\/\/www.microsoft.com\/technet\/security\/guidance\/PatchManagement.mspx](http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx).  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)