---
title: "ActivationFactory::GetTrustLevel-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ActivationFactory::GetTrustLevel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetTrustLevel-Methode"
ms.assetid: 31547ae6-d2ab-4039-923c-154d53fb1a8b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ActivationFactory::GetTrustLevel-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft die Vertrauensebene des Objekts, das der aktuelle ActivationFactory instanziiert.  
  
## Syntax  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### Parameter  
 `trustLvl`  
 Wenn dieser Vorgang abgeschlossen ist, die Vertrauensebene der Laufzeitklasse, die der ActivationFactory instanziiert.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; Andernfalls wird ein Assertionsfehler ausgegeben und `trustLvl` wird auf "FullTrust" festgelegt.  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ActivationFactory\-Klasse](../windows/activationfactory-class.md)