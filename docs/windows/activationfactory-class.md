---
title: ActivationFactory-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- ActivationFactory class
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e6088ec152d7c91cb06c17c9dae2698f2fd983d1
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610189"
---
# <a name="activationfactory-class"></a>ActivationFactory-Klasse

Ermöglicht, dass eine oder mehrere Klassen durch die Windows-Runtime aktiviert werden.

## <a name="syntax"></a>Syntax

```cpp
template <
   typename I0 = Details::Nil,
   typename I1 = Details::Nil,
   typename I2 = Details::Nil
>
class ActivationFactory : public Details::RuntimeClass<typename Details::InterfaceListHelper<IActivationFactory, I0, I1, I2, Details::Nil>::TypeT, RuntimeClassFlags<WinRt | InhibitWeakReference>, false>;
```

### <a name="parameters"></a>Parameter

*I0*  
Die nullte-Schnittstelle.

*I1*  
Die erste Schnittstelle.

*I2*  
Die zweite Schnittstelle.

## <a name="remarks"></a>Hinweise

**ActivationFactory** bietet Registrierungsmethoden und die grundlegende Funktionalität für die `IActivationFactory` Schnittstelle. **ActivationFactory** können Sie eine benutzerdefinierte Factory-Implementierung bereitzustellen.

Das folgende Codefragment veranschaulicht symbolisch ActivationFactory verwenden.

[!code-cpp[wrl-microsoft__wrl__activationfactory#1](../windows/codesnippet/CPP/activationfactory-class_1.cpp)]

Das folgende Codefragment zeigt, wie Sie mit der [implementiert](../windows/implements-structure.md) Struktur an mehr als drei Schnittstellen-IDs.

`struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[ActivationFactory::ActivationFactory-Konstruktor](../windows/activationfactory-activationfactory-constructor.md)|Initialisiert die **ActivationFactory** Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[ActivationFactory::AddRef-Methode](../windows/activationfactory-addref-method.md)|Inkrementiert den Verweiszähler des aktuellen **ActivationFactory** Objekt.|
|[ActivationFactory::GetIids-Methode](../windows/activationfactory-getiids-method.md)|Ruft ein Array von implementierten Schnittstellen-IDs ab.|
|[ActivationFactory::GetRuntimeClassName-Methode](../windows/activationfactory-getruntimeclassname-method.md)|Ruft den Common Language Runtime-Klassennamen des Objekts ab, die die aktuelle **ActivationFactory** instanziiert.|
|[ActivationFactory::GetTrustLevel-Methode](../windows/activationfactory-gettrustlevel-method.md)|Ruft der Vertrauensebene des Objekts ab, das aktuelle **ActivationFactory** instanziiert.|
|[ActivationFactory::QueryInterface-Methode](../windows/activationfactory-queryinterface-method.md)|Ruft einen Zeiger auf die angegebene Schnittstelle ab.|
|[ActivationFactory::Release-Methode](../windows/activationfactory-release-method.md)|Dekrementiert den Verweiszähler des aktuellen **ActivationFactory** Objekt.|

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

`ActivationFactory`

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)