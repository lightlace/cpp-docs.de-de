---
title: "Implements::FillArrayWithIid-Methode"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Implements::FillArrayWithIid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FillArrayWithIid-Methode"
ms.assetid: b2e62e3f-0ab9-4c70-aad7-856268544f44
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# Implements::FillArrayWithIid-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fügt die Schnittstellen\-ID ein, die durch den aktuellen zeroth Vorlagenparameter in das angegebene Arrayelement angegeben wird.  
  
## Syntax  
  
```  
__forceinline static void FillArrayWithIid(  
   unsigned long &index,  
   _In_ IID* iids  
);  
```  
  
#### Parameter  
 `index`  
 Ein nullbasierter Index, der den Ausgangsbedingungen Arrayelement für diesen Vorgang angibt.  Wenn dieser Vorgang abgeschlossen ist, wird `index` durch. 1 erhöht.  
  
 `iids`  
 Ein Array Typ IID.  
  
## Hinweise  
 Interne Hilfsfunktion.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Implements\-Struktur](../windows/implements-structure.md)