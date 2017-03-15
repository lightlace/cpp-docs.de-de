---
title: "AgileActivationFactory-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::AgileActivationFactory"
dev_langs: 
  - "C++"
ms.assetid: fab98f32-bb93-4c0f-badb-49fbddb194b0
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# AgileActivationFactory-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt eine Apartment\-benutzerfreundliche Aktivierungsfactory dar, die unter [FtmBase](../windows/ftmbase-class.md).  
  
## Syntax  
  
```cpp  
template <  
   typename I0 = Details::Nil,   
   typename I1 = Details::Nil,   
   typename I2 = Details::Nil,   
FactoryCacheFlags cacheFlagValue = FactoryCacheDefault>  
class AgileActivationFactory :   
   public ActivationFactory<Implements<FtmBase, I0>, I1, I2, cacheFlagValue>  
{};  
```  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)   
 [ActivationFactory\-Klasse](../windows/activationfactory-class.md)