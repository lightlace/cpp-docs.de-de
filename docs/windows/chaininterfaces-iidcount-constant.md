---
title: "ChainInterfaces::IidCount-Konstante"
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
  - "implements/Microsoft::WRL::ChainInterfaces::IidCount"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IidCount-Konstante"
ms.assetid: d4a90aa0-513c-4e99-b978-e12149734936
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# ChainInterfaces::IidCount-Konstante
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Gesamtanzahl von Schnittstellen\-IDs enthalten in Schnittstellen angegeben durch Vorlagenparameter `I0` durch `I9`.  
  
## Syntax  
  
```  
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;  
```  
  
## Rückgabewert  
 Die Gesamtanzahl der Schnittstellen\-IDs.  
  
## Hinweise  
 Vorlagenparameter `I0` und `I1` sind erforderlich, Parameter und `I2` von `I9` sind optional. Die IID\-Anzahl jeder Schnittstelle ist in der Regel 1.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ChainInterfaces\-Struktur](../windows/chaininterfaces-structure.md)