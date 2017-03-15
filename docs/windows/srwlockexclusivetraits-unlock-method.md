---
title: "SRWLockExclusiveTraits::Unlock-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unlock-Methode"
ms.assetid: 7fd6b0fb-8b88-4a43-aa74-0d7fe47a0da6
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SRWLockExclusiveTraits::Unlock-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt Alleinherrschaft des angegebenen SRWLock\-Objekts frei.  
  
## Syntax  
  
```  
inline static void Unlock(  
   _In_ Type srwlock  
);  
```  
  
#### Parameter  
 `srwlock`  
 Handle für ein SRWLock\-Objekt.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:**  Microsoft::WRL::Wrappers::HandleTraits  
  
## Siehe auch  
 [SRWLockExclusiveTraits\-Struktur](../windows/srwlockexclusivetraits-structure.md)