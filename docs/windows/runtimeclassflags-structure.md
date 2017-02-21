---
title: "RuntimeClassFlags-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClassFlags"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RuntimeClassFlags-Struktur"
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# RuntimeClassFlags-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Enthält den Typ für eine Instanz von [RuntimeClass](../windows/runtimeclass-class.md).  
  
## Syntax  
  
```  
template <  
   unsigned int flags  
>  
struct RuntimeClassFlags;  
```  
  
#### Parameter  
 `flags`  
 Ein [RuntimeClassType\-Enumeration](../windows/runtimeclasstype-enumeration.md)\-Wert.  
  
## Member  
  
### Öffentliche Konstanten  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[RuntimeClassFlags::value\-Konstante](../windows/runtimeclassflags-value-constant.md)|[RuntimeClassType\-Enumeration](../windows/runtimeclasstype-enumeration.md) Enthält einen Wert.|  
  
## Vererbungshierarchie  
 `RuntimeClassFlags`  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)