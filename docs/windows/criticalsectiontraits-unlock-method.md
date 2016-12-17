---
title: "CriticalSectionTraits::Unlock-Methode"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unlock-Methode"
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# CriticalSectionTraits::Unlock-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spezialisiert eine CriticalSections\-Vorlage, sodass sie das Freigeben des Besitzes des angegebenen Abschnittsobjekts kritischen unterstützt.  
  
## Syntax  
  
```  
inline static void Unlock(  
   _In_ Type cs  
);  
```  
  
#### Parameter  
 `cs`  
 Ein Zeiger zu einem kritischen Abschnittsobjekt.  
  
## Hinweise  
 Der *Type*\-Modifizierer wird als `typedef CRITICAL_SECTION* Type;` definiert.  
  
 Weitere Informationen finden Sie unter "LeaveCriticalSections\-Funktion" im "Synchronisierungs\-Funktions" Abschnitt der Windows\-API\-Dokumentation.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:**  Microsoft::WRL::Wrappers::HandleTraits  
  
## Siehe auch  
 [CriticalSectionTraits\-Struktur](../windows/criticalsectiontraits-structure.md)