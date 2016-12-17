---
title: "VerifyInheritanceHelper-Struktur"
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
  - "implements/Microsoft::WRL::Details::VerifyInheritanceHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VerifyInheritanceHelper-Struktur"
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# VerifyInheritanceHelper-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template <  
   typename I,  
   typename Base  
>  
struct VerifyInheritanceHelper;  
template <  
   typename I  
>  
struct VerifyInheritanceHelper<I, Nil>;  
```  
  
#### Parameter  
 `I`  
 Ein Typ.  
  
 `Base`  
 Andere geben ein.  
  
## Hinweise  
 Testet, dass eine Schnittstelle von einer anderen Schnittstelle abgeleitet wird.  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[VerifyInheritanceHelper::Verify\-Methode](../windows/verifyinheritancehelper-verify-method.md)|Testet die beiden Schnittstellen, die von der aktuellen Vorlagenparameter angegeben werden und bestimmt, ob eine Schnittstelle von anderen abgeleitet wird.|  
  
## Vererbungshierarchie  
 `VerifyInheritanceHelper`  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)