---
title: "SimpleActivationFactory::GetRuntimeClassName-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName"
dev_langs: 
  - "C++"
ms.assetid: 3aa07487-9a42-46f8-8893-37ba6315e50b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SimpleActivationFactory::GetRuntimeClassName-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft den Ablaufklassennamen eine Instanz der Klasse ab, die durch den `Base`\-Klassenvorlagenparameter angegeben wird.  
  
## Syntax  
  
```  
STDMETHOD(  
   GetRuntimeClassName  
)(_Out_ HSTRING* runtimeName);  
```  
  
#### Parameter  
 `runtimeName`  
 Wenn dieser Vorgang abgeschlossen wurde, der Ablaufklassenname.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## Hinweise  
 Wenn \_\_WRL\_STRICT definiert wird, wird ein Assertionsfehler, ausgegeben, wenn die Klasse, die von den `Base`\-Klassenvorlagenparameter angegeben ist, nicht von [RuntimeClass](../windows/runtimeclass-class.md) abgeleitet wird, oder wird nicht mit dem WinRt Enumerationswert oder WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) konfiguriert.  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [SimpleActivationFactory\-Klasse](../windows/simpleactivationfactory-class.md)