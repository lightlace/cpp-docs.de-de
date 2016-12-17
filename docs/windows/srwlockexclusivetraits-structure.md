---
title: "SRWLockExclusiveTraits-Struktur"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SRWLockExclusiveTraits-Struktur"
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# SRWLockExclusiveTraits-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt allgemeine Eigenschaften der SRWLock\-Klasse im exklusiven Sperrenmodus.  
  
## Syntax  
  
```  
struct SRWLockExclusiveTraits;  
```  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`Type`|Synonym für [SRWLOCK](../windows/srwlock-class.md) einen Zeiger auf die Klasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[SRWLockExclusiveTraits::GetInvalidValue\-Methode](../windows/srwlockexclusivetraits-getinvalidvalue-method.md)|Ruft ein SRWLockExclusiveTraits\-Objekt ab, die immer ungültig ist.|  
|[SRWLockExclusiveTraits::Unlock\-Methode](../windows/srwlockexclusivetraits-unlock-method.md)|Gibt Alleinherrschaft des angegebenen SRWLock\-Objekts frei.|  
  
## Vererbungshierarchie  
 `SRWLockExclusiveTraits`  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:**  Microsoft::WRL::Wrappers::HandleTraits  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers::HandleTraits\-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)