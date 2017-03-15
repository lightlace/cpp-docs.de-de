---
title: "/WINMDKEYCONTAINER (Schl&#252;sselcontainer angeben) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.WINMDKEYCONTAINER"
dev_langs: 
  - "C++"
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /WINMDKEYCONTAINER (Schl&#252;sselcontainer angeben)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Schlüsselcontainer an, um eine Datei Windows\-Metadaten zu signieren \(.winmd\).  
  
```  
  
/WINMDKEYCONTAINER:name  
  
```  
  
## Hinweise  
 Ähnelt der Linkeroption [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md), die für die Datei \(.winmd\) angewendet wird.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **Linker** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Windows\-Metadaten** aus.  
  
4.  Im Feld **Windows\-Metadaten\-Schlüsselcontainer** den Speicherort ein.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)