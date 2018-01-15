---
title: ClassFactory-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::ClassFactory
dev_langs: C++
helpviewer_keywords: ClassFactory class
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8c37c016809d31fcb072f23768e9f54313331016
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="classfactory-class"></a>ClassFactory-Klasse
Implementiert die grundlegende Funktion der IClassFactory-Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `I0`  
 Die nullte-Schnittstelle.  
  
 `I1`  
 Die erste Schnittstelle.  
  
 `I2`  
 Die zweite Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie `ClassFactory` eine benutzerdefinierte Factoryimplementierung zur Verfügung gestellt.  
  
 Die folgenden programmierschema veranschaulicht, wie die [implementiert](../windows/implements-structure.md) Struktur, um mehr als drei Schnittstellen auf einer Klassenfactory anzugeben.  
  
 `struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ClassFactory::ClassFactory-Konstruktor](../windows/classfactory-classfactory-constructor.md)||  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ClassFactory::AddRef-Methode](../windows/classfactory-addref-method.md)|Inkrementiert den Verweiszähler für das aktuelle ClassFactory-Objekt.|  
|[ClassFactory::LockServer-Methode](../windows/classfactory-lockserver-method.md)|Erhöht oder verringert die Anzahl der zugrunde liegenden Objekte, die vom aktuellen Objekt ClassFactory nachverfolgt werden.|  
|[ClassFactory::QueryInterface-Methode](../windows/classfactory-queryinterface-method.md)|Ruft einen Zeiger auf die Schnittstelle, die durch Parameter angegeben wird.|  
|[ClassFactory::Release-Methode](../windows/classfactory-release-method.md)|Dekrementiert den Verweiszähler für das aktuelle ClassFactory-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
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
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft:: wrl-Namespace](../windows/microsoft-wrl-namespace.md)   
 [RuntimeClassType-Enumeration](../windows/runtimeclasstype-enumeration.md)