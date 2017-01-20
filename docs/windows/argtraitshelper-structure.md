---
title: "ArgTraitsHelper-Struktur"
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
  - "event/Microsoft::WRL::Details::ArgTraitsHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ArgTraitsHelper-Struktur"
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
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