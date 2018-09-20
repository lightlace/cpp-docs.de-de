---
title: InterfaceTraits-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits
dev_langs:
- C++
helpviewer_keywords:
- InterfaceTraits structure
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cb8eb8fbc4199ccdaf5717e465f202c0e4ec296e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437643"
---
# <a name="interfacetraits-structure"></a>InterfaceTraits-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template<
   typename I0
>
struct __declspec(novtable) InterfaceTraits;
template<typename CloakedType>
struct __declspec(novtable) InterfaceTraits<CloakedIid<CloakedType>>;

template<>
struct __declspec(novtable) InterfaceTraits<Nil>;
```

### <a name="parameters"></a>Parameter

*I0*<br/>
Der Name einer Schnittstelle.

*CloakedType*<br/>
Für `RuntimeClass`, `Implements` und `ChainInterfaces`, eine Schnittstelle, die in der Liste der nicht unterstützten Schnittstellen-IDs.

## <a name="remarks"></a>Hinweise

Implementiert die allgemeinen Merkmale einer Schnittstelle.

Die zweite Vorlage ist eine Spezialisierung für die verdeckten Schnittstellen. Die dritte Vorlage ist eine Spezialisierung für NULL-Parameter.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`Base`|Ein Synonym für den *I0* Template-Parameter.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[InterfaceTraits::CanCastTo-Methode](../windows/interfacetraits-cancastto-method.md)|Gibt an, ob der angegebene Zeiger umgewandelt werden kann, auf einen Zeiger auf `Base`.|
|[InterfaceTraits::CastToBase-Methode](../windows/interfacetraits-casttobase-method.md)|Wandelt den angegebenen Zeiger auf einen Zeiger auf `Base`.|
|[InterfaceTraits::CastToUnknown-Methode](../windows/interfacetraits-casttounknown-method.md)|Wandelt den angegebenen Zeiger auf einen Zeiger auf `IUnknown`.|
|[InterfaceTraits::FillArrayWithIid-Methode](../windows/interfacetraits-fillarraywithiid-method.md)|Weist die Schnittstellen-ID des `Base` auf das Arrayelement, das durch die Indexargument angegeben wird.|
|[InterfaceTraits::Verify-Methode](../windows/interfacetraits-verify-method.md)|Überprüft, ob `Base` ordnungsgemäß abgeleitet ist.|

### <a name="public-constants"></a>Öffentliche Konstanten

|name|Beschreibung|
|----------|-----------------|
|[InterfaceTraits::IidCount-Konstant](../windows/interfacetraits-iidcount-constant.md)|Enthält die Anzahl der Schnittstellen-IDs im Zusammenhang mit der aktuellen **InterfaceTraits** Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`InterfaceTraits`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)