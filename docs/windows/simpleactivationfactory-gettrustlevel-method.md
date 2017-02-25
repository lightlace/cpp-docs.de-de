---
title: "SimpleActivationFactory::GetTrustLevel-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel"
dev_langs: 
  - "C++"
ms.assetid: 99aa9bc9-d954-4a6f-902b-4abe00e43039
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SimpleActivationFactory::GetTrustLevel-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft die Vertrauensebene einer Instanz der Klasse ab, die durch den `Base`\-Klassenvorlagenparameter angegeben wird.  
  
## Syntax  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### Parameter  
 `trustLvl`  
 Wenn dieser Vorgang abgeschlossen ist, die Vertrauensebene des aktuellen Klassenobjekts.  
  
## Rückgabewert  
 Immer S\_OK.  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [SimpleActivationFactory\-Klasse](../windows/simpleactivationfactory-class.md)