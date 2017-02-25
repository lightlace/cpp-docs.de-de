---
title: "CriticalSectionTraits::GetInvalidValue-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInvalidValue-Methode"
ms.assetid: 665f30a6-ca9c-4968-8c03-8f84e6b2329b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
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