---
title: "SemaphoreTraits-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SemaphoreTraits-Struktur"
ms.assetid: eddb8576-d063-409b-9201-cc87ca5d111e
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SemaphoreTraits-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert allgemeine Eigenschaften eines Semaphorobjekts.  
  
## Syntax  
  
```  
struct SemaphoreTraits : HANDLENullTraits;  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[SemaphoreTraits::Unlock\-Methode](../windows/semaphoretraits-unlock-method.md)|Versionssteuerelement einer freigegebenen Ressource.|  
  
## Vererbungshierarchie  
 `HANDLENullTraits`  
  
 `SemaphoreTraits`  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:**  Microsoft::WRL::Wrappers::HandleTraits  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers::HandleTraits\-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)