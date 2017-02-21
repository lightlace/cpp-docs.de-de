---
title: "SimpleActivationFactory::ActivateInstance-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivateInstance-Methode"
ms.assetid: 4f836e51-5a6c-4bad-b871-9f25199298b4
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SimpleActivationFactory::ActivateInstance-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt eine Instanz die angegebene Schnittstelle.  
  
## Syntax  
  
```  
STDMETHOD(  
   ActivateInstance  
)(_Deref_out_ IInspectable **ppvObject);  
```  
  
#### Parameter  
 `ppvObject`  
 Wenn dieser Vorgang abgeschlossen hat, wurden Zeiger auf eine Instanz des Objekts durch den `Base`\-Klassenvorlagenparameter an.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## Hinweise  
 Wenn \_\_WRL\_STRICT definiert wird, wird ein Assertionsfehler, ausgegeben, wenn die Basisklasse, die im Klassenvorlagenparameter angegeben ist, nicht von [RuntimeClass](../windows/runtimeclass-class.md) abgeleitet wird, oder wird nicht mit dem WinRt Enumerationswert oder WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) konfiguriert.  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [SimpleActivationFactory\-Klasse](../windows/simpleactivationfactory-class.md)