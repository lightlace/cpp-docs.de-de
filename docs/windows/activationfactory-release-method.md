---
title: "ActivationFactory::Release-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ActivationFactory::Release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Release-Methode"
ms.assetid: 5bc25ff0-ee3c-4a2d-a9b6-2d8f158033ad
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ActivationFactory::Release-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dekrementiert den Verweiszählerwert des aktuellen ActivationFactory\-Objekts.  
  
## Syntax  
  
```  
STDMETHOD_(  
   ULONG,  
   Release  
)();  
```  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler beschreibt.  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ActivationFactory\-Klasse](../windows/activationfactory-class.md)