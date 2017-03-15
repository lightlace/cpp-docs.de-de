---
title: "SimpleActivationFactory-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::SimpleActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SimpleActivationFactory-Klasse"
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# SimpleActivationFactory-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt einen einfachen Mechanismus bereit, um eine Windows Runtime oder klassische Eine COM\-Basisklasse zu erstellen.  
  
## Syntax  
  
```  
template<  
   typename Base  
>  
class SimpleActivationFactory : public ActivationFactory<>;  
```  
  
#### Parameter  
 `Base`  
 Eine Basisklasse.  
  
## Hinweise  
 Die Basisklasse muss einen Standardkonstruktor bereitstellen.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie SimpleActivationFactory mit dem Makro [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) verwendet.  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[SimpleActivationFactory::ActivateInstance\-Methode](../windows/simpleactivationfactory-activateinstance-method.md)|Erstellt eine Instanz die angegebene Schnittstelle.|  
|[SimpleActivationFactory::GetRuntimeClassName\-Methode](../windows/simpleactivationfactory-getruntimeclassname-method.md)|Ruft den Ablaufklassennamen eine Instanz der Klasse ab, die durch den `Base`\-Klassenvorlagenparameter angegeben wird.|  
|[SimpleActivationFactory::GetTrustLevel\-Methode](../windows/simpleactivationfactory-gettrustlevel-method.md)|Ruft die Vertrauensebene einer Instanz der Klasse ab, die durch den `Base`\-Klassenvorlagenparameter angegeben wird.|  
  
## Vererbungshierarchie  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ActivationFactory`  
  
 `SimpleActivationFactory`  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)