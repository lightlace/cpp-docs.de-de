---
title: "RuntimeClassBaseT-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::RuntimeClassBaseT"
dev_langs: 
  - "C++"
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# RuntimeClassBaseT-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template <  
   unsigned int RuntimeClassTypeT  
>  
friend struct Details::RuntimeClassBaseT;  
```  
  
#### Parameter  
 `RuntimeClassTypeT`  
 Ein Feld von Flags, das einen oder mehreren [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) Enumeratoren angibt.  
  
## Hinweise  
 Stellt `QueryInterface` Hilfsmethoden für Vorgänge und Abrufenschnittstellen\-ids bereit.  
  
## Member  
  
## Vererbungshierarchie  
 `RuntimeClassBaseT`  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Reference \(Windows Runtime Library\)](assetId:///00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)