---
title: "Mehrere Ziele | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Makefiles und Ziele"
  - "Mehrere Ziele in NMAKE"
  - "Ziele, mehrere in NMAKE"
  - "NMAKE (Programm), Ziele"
ms.assetid: b609a179-0b9f-4b08-9930-998047588ae0
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Mehrere Ziele
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE wertet mehrere Ziele in einer einzelnen Abhängigkeit als jeweils in einer separaten Beschreibungsblöcken angegeben wurden.  
  
 Dies z. B....  
  
```Output  
bounce.exe leap.exe : jump.obj  
   echo Building...  
```  
  
 .. Auswertung:  
  
```Output  
bounce.exe : jump.obj  
   echo Building...  
leap.exe : jump.obj  
   echo Building...  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ziele](../build/targets.md)