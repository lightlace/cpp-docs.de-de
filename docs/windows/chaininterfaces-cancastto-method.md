---
title: "ChainInterfaces::CanCastTo-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::ChainInterfaces::CanCastTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanCastTo-Methode"
ms.assetid: 8be44875-53ed-494b-91a0-0f8e399685bb
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ChainInterfaces::CanCastTo-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob die angegebene Schnittstellen\-ID zu jeder der Normalisierungsformen Spezialisierungen umgewandelt werden kann, die von den nicht standardmäßigen Vorlagenparameter definiert werden.  
  
## Syntax  
  
```  
__forceinline bool CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### Parameter  
 `riid`  
 Eine Schnittstelle ID  
  
 `ppv`  
 Ein Zeiger zur letzten Schnittstellen\-ID, die erfolgreich umgewandelt wurde.  
  
## Rückgabewert  
 `true`, wenn alle Umwandlungsvorgänge gehalten haben; andernfalls `false`.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ChainInterfaces\-Struktur](../windows/chaininterfaces-structure.md)