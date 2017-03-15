---
title: "ChainInterfaces::FillArrayWithIid-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::ChainInterfaces::FillArrayWithIid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FillArrayWithIid-Methode"
ms.assetid: f1ce699c-dfb6-40a9-9ea0-e6703d3cf971
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ChainInterfaces::FillArrayWithIid-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Speichert die Schnittstellen\-ID, die von den `I0` Vorlagenparameter an die angegebene Position in einem angegebenen Array Schnittstellen\-IDs definiert wird.  
  
## Syntax  
  
```  
__forceinline static void FillArrayWithIid(  
   _Inout_ unsigned long &index,  
   _In_ IID* iids  
);  
```  
  
#### Parameter  
 `index`  
 Zeiger zu einem Indexwert in das `iids` \- Array.  
  
 `iids`  
 Ein Array Schnittstellen\-IDs.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ChainInterfaces\-Struktur](../windows/chaininterfaces-structure.md)