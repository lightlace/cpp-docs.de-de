---
title: "IsSame-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::IsSame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsSame-Struktur"
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# IsSame-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template <  
   typename T1,  
   typename T2  
>  
struct IsSame;  
template <  
   typename T1  
>  
struct IsSame<T1, T1>;  
```  
  
#### Parameter  
 `T1`  
 Ein Typ.  
  
 `T2`  
 Andere geben ein.  
  
## Hinweise  
 Testet, ob ein angegebener Typ identisch mit einem anderen bestimmten Typ ist.  
  
## Member  
  
### Öffentliche Konstanten  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[IsSame::value\-Konstante](../windows/issame-value-constant.md)|Gibt an, ob ein Typ der gleiche wie andere.|  
  
## Vererbungshierarchie  
 `IsSame`  
  
## Anforderungen  
 **Header:**  internal.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)