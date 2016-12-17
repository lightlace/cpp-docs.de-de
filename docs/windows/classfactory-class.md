---
title: "ClassFactory-Klasse"
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
  - "module/Microsoft::WRL::ClassFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ClassFactory-Klasse"
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# ClassFactory-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Implementiert die grundlegende Funktion der IClassFactory\-Schnittstelle.  
  
## Syntax  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ClassFactory : public Details::RuntimeClass<  
   typename Details::InterfaceListHelper<IClassFactory,   
   I0,   
   I1,   
   I2,   
   Details::Nil>::TypeT,   
   RuntimeClassFlags<ClassicCom | InhibitWeakReference>,   
      false>;  
```  
  
#### Parameter  
 `I0`  
 Die zeroth Schnittstelle.  
  
 `I1`  
 Die erste Schnittstelle.  
  
 `I2`  
 Die zweite Schnittstelle.  
  
## Hinweise  
 Verwenden Sie `ClassFactory`, um eine benutzerdefinierte Factoryimplementierung bereitzustellen.  
  
 Im folgenden Programmierungsmuster zeigt, wie die [Implementiert](../windows/implements-structure.md)\-Struktur verwendet, um mehr als drei Schnittstellen auf einer Klassenfactory anzugeben.  
  
 `struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ClassFactory::ClassFactory\-Konstruktor](../windows/classfactory-classfactory-constructor.md)||  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ClassFactory::AddRef\-Methode](../windows/classfactory-addref-method.md)|Inkrementiert den Verweiszähler für das aktuelle ClassFactory\-Objekt.|  
|[ClassFactory::LockServer\-Methode](../windows/classfactory-lockserver-method.md)|Inkrementiert oder wird die Anzahl der zugrunde liegenden Objekte, die vom aktuellen ClassFactory\-Objekt nachverfolgt werden.|  
|[ClassFactory::QueryInterface\-Methode](../windows/classfactory-queryinterface-method.md)|Ruft einen Zeiger auf eine Schnittstelle ab, die durch Parameter angegeben wird.|  
|[ClassFactory::Release\-Methode](../windows/classfactory-release-method.md)|Dekrementiert den Verweiszähler für das aktuelle ClassFactory\-Objekt.|  
  
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
  
 `ClassFactory`  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)   
 [RuntimeClassType\-Enumeration](../windows/runtimeclasstype-enumeration.md)