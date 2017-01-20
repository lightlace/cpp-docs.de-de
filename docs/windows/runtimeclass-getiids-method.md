---
title: "RuntimeClass::GetIids-Methode"
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
  - "implements/Microsoft::WRL::RuntimeClass::GetIids"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetIids-Methode"
ms.assetid: 826a67d1-ebc4-4940-b5d5-7cd66885e4a1
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClass::GetIids-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft ein Array ab, das die Schnittstellen\-IDs enthalten kann, die durch das aktuelle RuntimeClass\-Objekt implementiert werden.  
  
## Syntax  
  
```  
STDMETHOD(  
   GetIids  
)  
   (_Out_ ULONG *iidCount,   
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
#### Parameter  
 `iidCount`  
 Wenn dieser Vorgang abgeschlossen ist, die Gesamtanzahl von Elementen im Array `iids`.  
  
 `iids`  
 Wenn dieser Vorgang abgeschlossen ist, ein Zeiger auf ein Array Schnittstellen\-IDs.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls E\_OUTOFMEMORY.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [RuntimeClass\-Klasse](../windows/runtimeclass-class.md)