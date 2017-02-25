---
title: "SemaphoreTraits::Unlock-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unlock-Methode"
ms.assetid: 4e0ea808-b70d-43f7-81ef-998c3b34e3a0
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SemaphoreTraits::Unlock-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Versionssteuerelement einer freigegebenen Ressource.  
  
## Syntax  
  
```  
inline static void Unlock(  
   _In_ Type h  
);  
```  
  
#### Parameter  
 `h`  
 Handle für ein Semaphorobjekt.  
  
## Hinweise  
 Wenn der entsperrensvorgang fehlschlägt, gibt Unlock\(\) einen Fehler aus, der die Fehlerursache angibt.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:**  Microsoft::WRL::Wrappers::HandleTraits  
  
## Siehe auch  
 [SemaphoreTraits\-Struktur](../windows/semaphoretraits-structure.md)