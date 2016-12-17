---
title: "ActivationFactory::GetTrustLevel-Methode"
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
  - "module/Microsoft::WRL::ActivationFactory::GetTrustLevel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetTrustLevel-Methode"
ms.assetid: 31547ae6-d2ab-4039-923c-154d53fb1a8b
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
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