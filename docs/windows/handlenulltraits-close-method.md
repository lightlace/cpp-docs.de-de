---
title: "HANDLENullTraits::Close-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close-Methode"
ms.assetid: 6fb2fa0d-df20-45dc-856f-f78497f8bdf9
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# HANDLENullTraits::Close-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Schließt das angegebene Handle.  
  
## Syntax  
  
```  
inline static bool Close(  
   _In_ Type h  
);  
```  
  
#### Parameter  
 `h`  
 Das Handle zu schließen.  
  
## Rückgabewert  
 **true**, wenn `h` erfolgreich Handle geschlossen hat; andernfalls **false**.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:**  Microsoft::WRL::Wrappers::HandleTraits  
  
## Siehe auch  
 [HANDLENullTraits\-Struktur](../windows/handlenulltraits-structure.md)