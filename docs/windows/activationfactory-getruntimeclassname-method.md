---
title: "ActivationFactory::GetRuntimeClassName-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ActivationFactory::GetRuntimeClassName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRuntimeClassName-Methode"
ms.assetid: 74e34f0a-9c51-4b40-89f5-45c6c5886ece
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ActivationFactory::GetRuntimeClassName-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft den Ablaufklassennamen des Objekts, das der aktuelle ActivationFactory instanziiert.  
  
## Syntax  
  
```  
STDMETHOD(  
   GetRuntimeClassName  
)(_Out_ HSTRING* runtimeName);  
```  
  
#### Parameter  
 `runtimeName`  
 Wenn dieser Vorgang abgeschlossen ist, ein Handle einer Zeichenfolge, die den Ablaufklassennamen des Objekts enthält, das der aktuelle ActivationFactory instanziiert.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler beschreibt.  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ActivationFactory\-Klasse](../windows/activationfactory-class.md)