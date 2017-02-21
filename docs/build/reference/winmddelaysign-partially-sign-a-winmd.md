---
title: "/WINMDDELAYSIGN (eine winmd teilweise signieren) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.WINMDDelaySign"
dev_langs: 
  - "C++"
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /WINMDDELAYSIGN (eine winmd teilweise signieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aktiviert eine teilweise Signierung von eine Windows \(.winmd Runtime\-Metadaten\) festzulegen durch Einfügen des öffentlichen Schlüssels in die Datei.  
  
```  
  
/WINMDDELAYSIGN[:NO]  
  
```  
  
## Hinweise  
 Ähnelt der Linkeroption [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md), die der WINMD\-Datei angewendet wird.  Verwenden Sie **\/WINMDDELAYSIGN**, wenn Sie nur den öffentlichen Schlüssel in die WINMD\-Datei einfügen möchten.  Standardmäßig fungiert der Linker, als ob **\/WINMDDELAYSIGN:NO** angegeben wurden; das heißt, signiert der nicht die winmd Datei.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **Linker** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Windows\-Metadaten** aus.  
  
4.  Im Dropdown\-Listenfeld **Verzögertes Signieren von Windows\-Metadaten** wählen Sie die Option aus, die Sie suchen.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)