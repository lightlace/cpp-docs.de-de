---
title: "RuntimeClass::Release-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClass::Release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Release-Methode"
ms.assetid: 0bd6f9e2-ad90-4de6-adef-a6286f458cb6
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# RuntimeClass::Release-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Führt eine COM\-Befreiungsaktion auf dem aktuellen RuntimeClass\-Objekt aus.  
  
## Syntax  
  
```  
STDMETHOD_(  
   ULONG,  
   Release  
)();  
```  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## Hinweise  
 Wenn der Verweiszähler null ist, wird das RuntimeClass\-Objekt gelöscht.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [RuntimeClass\-Klasse](../windows/runtimeclass-class.md)