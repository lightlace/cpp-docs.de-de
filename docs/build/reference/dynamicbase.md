---
title: "/DYNAMICBASE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/dynamicbase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DYNAMICBASE (editbin-Option)"
  - "DYNAMICBASE (editbin-Option)"
  - "-DYNAMICBASE (editbin-Option)"
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /DYNAMICBASE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob ein ausführbares Image generiert werden soll, für das zur Ladezeit mit ASLR \(Address Space Layout Randomization\) nach dem Zufallsprinzip ein Rebase\-Vorgang ausgeführt werden kann.  
  
## Syntax  
  
```  
  
/DYNAMICBASE[:NO]  
```  
  
## Hinweise  
 Standardmäßig legt der Verknüpfer die **\/DYNAMICBASE**\-Option fest.  
  
 Diese Option ändert den Header eines ausführbaren Images, um anzugeben, ob das Ladeprogramm für das Image nach dem Zufallsprinzip zur Ladezeit ein Rebase\-Vorgang ausgeführt werden kann.  
  
 ASLR wird unter Windows Vista, Windows Server 2008, Windows 7, Windows 8 und Windows Server 2012 unterstützt.  
  
## Siehe auch  
 [EDITBIN\-Optionen](../../build/reference/editbin-options.md)   
 [Windows\-ISV\-Softwaresicherheit](http://msdn.microsoft.com/library/bb430720.aspx)