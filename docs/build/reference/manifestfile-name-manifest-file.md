---
title: "/MANIFESTFILE (Benennen der Manifestdatei) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.ManifestFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFESTFILE (Linkeroption)"
  - "MANIFESTFILE (Linkeroption)"
  - "-MANIFESTFILE (Linkeroption)"
ms.assetid: befa5ab2-a9cf-4c9b-969a-e7b4a930f08d
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /MANIFESTFILE (Benennen der Manifestdatei)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MANIFESTFILE:filename  
```  
  
## Hinweise  
 Mithilfe von \/MANIFESTFILE können Sie den Standardnamen der Manifestdatei ändern.  Der Standardname der Manifestdatei ist der Dateiname, dem ".manifest" angehängt ist.  
  
 \/MANIFESTFILE hat keine Auswirkungen, wenn Sie nicht zusätzlich [\/MANIFEST](../../build/reference/manifest-create-side-by-side-assembly-manifest.md) verwenden.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **Linker**.  
  
4.  Wählen Sie die Eigenschaftenseite **Manifestdatei** aus.  
  
5.  Ändern Sie die Eigenschaft **Manifestdatei**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ManifestFile*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)