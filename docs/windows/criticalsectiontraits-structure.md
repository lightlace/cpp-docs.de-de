---
title: "CriticalSectionTraits-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CriticalSectionTraits-Struktur"
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# CriticalSectionTraits-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spezialisiert ein CriticalSections\-Objekt, um entweder einen ungültigen kritischen Abschnitt oder eine Funktion zu unterstützen, um einen kritischen Abschnitt freizugeben.  
  
## Syntax  
  
```  
struct CriticalSectionTraits;  
```  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`Type`|`typedef`, das einen Zeiger zu einem kritischen Abschnitt definiert.  `Type` wird als `typedef CRITICAL_SECTION* Type;` definiert.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[CriticalSectionTraits::GetInvalidValue\-Methode](../windows/criticalsectiontraits-getinvalidvalue-method.md)|Spezialisiert eine CriticalSections\-Vorlage, damit die Vorlage immer ungültig ist.|  
|[CriticalSectionTraits::Unlock\-Methode](../windows/criticalsectiontraits-unlock-method.md)|Spezialisiert eine CriticalSections\-Vorlage, sodass sie das Freigeben des Besitzes des angegebenen Abschnittsobjekts kritischen unterstützt.|  
  
## Vererbungshierarchie  
 `CriticalSectionTraits`  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:**  Microsoft::WRL::Wrappers::HandleTraits  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers::HandleTraits\-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)