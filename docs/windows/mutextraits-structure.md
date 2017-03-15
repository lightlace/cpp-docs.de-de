---
title: "MutexTraits-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MutexTraits-Struktur"
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# MutexTraits-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert allgemeine Eigenschaften der Klasse [Mutex](../windows/mutex-class1.md).  
  
## Syntax  
  
```  
struct MutexTraits : HANDLENullTraits;  
  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[MutexTraits::Unlock\-Methode](../windows/mutextraits-unlock-method.md)|Gibt Alleinherrschaft einer freigegebenen Ressource frei.|  
  
## Vererbungshierarchie  
 `HANDLENullTraits`  
  
 `MutexTraits`  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:**  Microsoft::WRL::Wrappers::HandleTraits  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers::HandleTraits\-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)