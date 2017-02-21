---
title: "ChainInterfaces::CastToUnknown-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::ChainInterfaces::CastToUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CastToUnknown-Methode"
ms.assetid: a6a58555-e5b0-4773-aba0-959d9d362c6b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ChainInterfaces::CastToUnknown-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wandelt den Schnittstellenzeiger vom Typ um, der vom `I0` Vorlagenparameter zu einem Zeiger auf IUnknown definiert wird.  
  
## Syntax  
  
```  
__forceinline IUnknown* CastToUnknown();  
```  
  
## Rückgabewert  
 Ein Zeiger auf IUnknown.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ChainInterfaces\-Struktur](../windows/chaininterfaces-structure.md)