---
title: "ArgTraitsHelper-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::ArgTraitsHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ArgTraitsHelper-Struktur"
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ArgTraitsHelper-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template<  
   typename TDelegateInterface  
>  
struct ArgTraitsHelper;  
```  
  
#### Parameter  
 `TDelegateInterface`  
 Eine Delegatschnittstelle.  
  
## Hinweise  
 Hilfen definieren allgemeine Eigenschaften von Delegatargumenten.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`methodType`|Ein Synonym für `decltype(&TDelegateInterface::Invoke)`.|  
|`Traits`|Ein Synonym für `ArgTraits<methodType>`.|  
  
### Öffentliche Konstanten  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ArgTraitsHelper::args\-Konstante](../windows/argtraitshelper-args-constant.md)|Hilfen [ArgTraits::args](../windows/argtraits-args-constant.md) halten die Anzahl der Parameter auf der Aufrufmethode einer Delegatschnittstelle.|  
  
## Vererbungshierarchie  
 `ArgTraitsHelper`  
  
## Anforderungen  
 **Header:** event.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)