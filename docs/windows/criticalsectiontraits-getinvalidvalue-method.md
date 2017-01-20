---
title: "CriticalSectionTraits::GetInvalidValue-Methode"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInvalidValue-Methode"
ms.assetid: 665f30a6-ca9c-4968-8c03-8f84e6b2329b
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# CriticalSectionTraits::GetInvalidValue-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spezialisiert eine CriticalSections\-Vorlage, damit die Vorlage immer ungültig ist.  
  
## Syntax  
  
```  
inline static Type GetInvalidValue();  
```  
  
## Rückgabewert  
 Gibt immer einen Zeiger auf einen ungültigen kritischen Abschnitt zurück.  
  
## Hinweise  
 Der *Type*\-Modifizierer wird als `typedef CRITICAL_SECTION* Type;` definiert.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:**  Microsoft::WRL::Wrappers::HandleTraits  
  
## Siehe auch  
 [CriticalSectionTraits\-Struktur](../windows/criticalsectiontraits-structure.md)