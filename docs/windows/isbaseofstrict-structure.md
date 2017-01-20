---
title: "IsBaseOfStrict-Struktur"
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
  - "internal/Microsoft::WRL::Details::IsBaseOfStrict"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsBaseOfStrict-Struktur"
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# IsBaseOfStrict-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template <  
   typename Base,  
   typename Derived  
>  
  
struct IsBaseOfStrict;  
template <  
   typename Base  
>  
struct IsBaseOfStrict<Base, Base>;  
```  
  
#### Parameter  
 `Base`  
 Der Basistyp.  
  
 `Derived`  
 Der abgeleitete Typ.  
  
## Hinweise  
 Testet, ob ein Typ Grundlage von anderen ist.  
  
 Die erste Vorlage überprüft wird, ob ein Typ von einem Basistyp abgeleitet wird, der auch **true** oder **false** führen kann.  Die zweite Vorlage überprüft wird, ob ein Typ sich von abgeleitet wird, der immer **false** ergibt.  
  
## Member  
  
### Öffentliche Konstanten  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[IsBaseOfStrict::value\-Konstante](../windows/isbaseofstrict-value-constant.md)|Gibt an, ob ein Typ Grundlage von anderen ist.|  
  
## Vererbungshierarchie  
 `IsBaseOfStrict`  
  
## Anforderungen  
 **Header:**  internal.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)