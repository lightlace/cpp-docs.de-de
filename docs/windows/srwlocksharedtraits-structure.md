---
title: "SRWLockSharedTraits-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SRWLockSharedTraits-Struktur"
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SRWLockSharedTraits-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt allgemeine Eigenschaften der SRWLock\-Klasse im Modus der gemeinsamen Sperre.  
  
## Syntax  
  
```  
struct SRWLockSharedTraits;  
```  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`Type`|Synonym für [SRWLOCK](../windows/srwlock-class.md) einen Zeiger auf die Klasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[SRWLockSharedTraits::GetInvalidValue\-Methode](../windows/srwlocksharedtraits-getinvalidvalue-method.md)|Ruft ein SRWLockSharedTraits\-Objekt ab, die immer ungültig ist.|  
|[SRWLockSharedTraits::Unlock\-Methode](../windows/srwlocksharedtraits-unlock-method.md)|Gibt Alleinherrschaft des angegebenen SRWLock\-Objekts frei.|  
  
## Vererbungshierarchie  
 `SRWLockSharedTraits`  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:**  Microsoft::WRL::Wrappers::HandleTraits  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers::HandleTraits\-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)