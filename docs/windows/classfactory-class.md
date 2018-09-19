---
title: ClassFactory-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory
dev_langs:
- C++
helpviewer_keywords:
- ClassFactory class
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0f033fc20fac656e6b9fcfa9ac822099ea929d62
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611804"
---
# <a name="classfactory-class"></a>ClassFactory-Klasse

Implementiert die grundlegende Funktion der `IClassFactory`-Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
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

### <a name="parameters"></a>Parameter

*I0*  
Die nullte-Schnittstelle.

*I1*  
Die erste Schnittstelle.

*I2*  
Die zweite Schnittstelle.

## <a name="remarks"></a>Hinweise

Nutzen **ClassFactory** eine benutzerdefinierte Factoryimplementierung bereitstellen.

Das folgende Muster für die Programmierung veranschaulicht, wie die [implementiert](../windows/implements-structure.md) Struktur, die mehr als drei Schnittstellen für eine Klassenfactory angeben.

`struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[ClassFactory::ClassFactory-Konstruktor](../windows/classfactory-classfactory-constructor.md)||

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[ClassFactory::AddRef-Methode](../windows/classfactory-addref-method.md)|Inkrementiert den Verweiszähler für den aktuellen **ClassFactory** Objekt.|
|[ClassFactory::LockServer-Methode](../windows/classfactory-lockserver-method.md)|Erhöht oder verringert die Anzahl der zugrunde liegenden Objekte nachverfolgt werden, von der aktuellen **ClassFactory** Objekt.|
|[ClassFactory::QueryInterface-Methode](../windows/classfactory-queryinterface-method.md)|Ruft einen Zeiger auf die Schnittstelle, die durch Parameter angegeben wird.|
|[ClassFactory::Release-Methode](../windows/classfactory-release-method.md)|Dekrementiert den Verweiszähler für den aktuellen **ClassFactory** Objekt.|

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

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)  
[RuntimeClassType-Enumeration](../windows/runtimeclasstype-enumeration.md)