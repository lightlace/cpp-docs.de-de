---
title: "ClassFactory::Release-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ClassFactory::Release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Release-Methode"
ms.assetid: 49da2002-f9d6-4d7f-8a65-48c20b1bf99f
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ClassFactory::Release-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dekrementiert den Verweiszähler für das aktuelle ClassFactory\-Objekt.  
  
## Syntax  
  
```  
STDMETHOD_(  
   ULONG,  
   Release  
)();  
```  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler beschreibt.  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ClassFactory\-Klasse](../windows/classfactory-class.md)