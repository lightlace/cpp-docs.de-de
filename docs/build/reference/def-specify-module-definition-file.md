---
title: "/DEF (Moduldefinitionsdatei festlegen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.ModuleDefinitionFile"
  - "/def"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DEF (Linkeroption)"
  - "DEF (Linkeroption)"
  - "-DEF (Linkeroption)"
  - "Moduldefinitionsdateien"
  - "Moduldefinitionsdateien, Angeben"
ms.assetid: 6497fa68-65f0-48ca-8f66-b87166fc631a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /DEF (Moduldefinitionsdatei festlegen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DEF:filename  
```  
  
## Hinweise  
 Hierbei ist:  
  
 *filename*  
 der Name einer an den Linker zu übergebenden Moduldefinitionsdatei \(DEF\-Datei\).  
  
## Hinweise  
 Die \/DEF\-Option übergibt eine Moduldefinitionsdatei \(.def\) an den Linker.  Nur eine DEF\-Datei kann in LINK angegeben werden.  Ausführliche Informationen über DEF\-Dateien finden Sie unter [Moduldefinitionsdateien](../../build/reference/module-definition-dot-def-files.md).  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Eingabe**.  
  
4.  Ändern Sie die Eigenschaft **Moduldefinition**.  
  
 Wenn Sie in der Entwicklungsumgebung eine DEF\-Datei angeben möchten, müssen Sie sie zusammen mit anderen Dateien in das Projekt einfügen und dann in der Option **\/DEF** angeben.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)