---
title: "/ALLOWISOLATION | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/ALLOWISOLATION"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ALLOWISOLATION (editbin-Option)"
  - "ALLOWISOLATION (editbin-Option)"
  - "-ALLOWISOLATION (editbin-Option)"
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /ALLOWISOLATION
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt das Verhalten bei der Manifestsuche an.  
  
## Syntax  
  
```  
  
/ALLOWISOLATION[:NO]  
```  
  
## Hinweise  
 **\/ALLOWISOLATION** bewirkt, dass das Betriebssysteme Manifestsuch\- und \-ladevorgänge durchführt.  
  
 Standardmäßig ist **\/ALLOWISOLATION** festgelegt.  
  
 **\/ALLOWISOLATION:NO** gibt an, dass ausführbare Dateien geladen werden, als wäre kein Manifest vorhanden, und bewirkt, dass [EDITBIN\-Referenz](../../build/reference/editbin-reference.md) `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION`\-Bit im optionalen `DllCharacteristics`\-Feld des Headers festlegt.  
  
 Wenn die Isolation für eine ausführbare Datei deaktiviert ist, führt das Windows\-Ladeprogramm keine Suche nach dem Anwendungsmanifest für den neu erstellen Prozess durch.  Der neue Prozess verfügt nicht über einen Standard\-Aktivierungskontext, selbst wenn ein Manifest in der ausführbaren Datei oder ein Manifest mit dem Namen *executable\-name*.exe.manifest vorhanden ist.  
  
## Siehe auch  
 [EDITBIN\-Optionen](../../build/reference/editbin-options.md)   
 [\/ALLOWISOLATION \(Manifestsuche\)](../../build/reference/allowisolation-manifest-lookup.md)   
 [Manifestdateienreferenz](http://msdn.microsoft.com/library/aa375632.aspx)