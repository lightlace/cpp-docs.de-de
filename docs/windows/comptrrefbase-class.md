---
title: ComPtrRefBase-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
- client/Microsoft::WRL::Details::ComPtrRefBase::ptr_
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRefBase class
- Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable** operator
- Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown** operator
- Microsoft::WRL::Details::ComPtrRefBase::ptr_ data member
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 79b7c3df2b6d3dc338ecda713b4ec406c8964cab
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789253"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase-Klasse

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <typename T>
class ComPtrRefBase;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Ein [ComPtr\<T >](../windows/comptr-class.md) Typ oder einem Typ abgeleitet ist, nicht nur die Schnittstelle der `ComPtr`.

## <a name="remarks"></a>Hinweise

Stellt die Basisklasse für die [ComPtrRef](../windows/comptrref-class.md) Klasse.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

Name            | Beschreibung
--------------- | -------------------------------------------------
`InterfaceType` | Ein Synonym für den Typ des Vorlagenparameters *T*.

### <a name="public-operators"></a>Öffentliche Operatoren

Name                                                                       | Beschreibung
-------------------------------------------------------------------------- | -----------------------------------------------------------------------------------------------------
[Comptrrefbase:: IInspectable **](#operator-iinspectable-star-star) | Wandelt das aktuelle [Ptr_](#ptr) Datenmembers, der einen Zeiger an eine-Zeiger-an die `IInspectable` Schnittstelle.
[Comptrrefbase:: IUnknown **](#operator-iunknown-star-star)         | Wandelt das aktuelle [Ptr_](#ptr) Datenmembers, der einen Zeiger an eine-Zeiger-an die `IUnknown` Schnittstelle.

### <a name="protected-data-members"></a>Geschützte Datenmember

name                        | Beschreibung
--------------------------- | ----------------------------------------------------------------
[Comptrrefbase:: Ptr_](#ptr) | Zeiger auf den Typ, durch den aktuellen Vorlagenparameter angegeben.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ComPtrRefBase`

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="operator-iinspectable-star-star"></a>Comptrrefbase:: "iinspectable"\* \* Operator

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
operator IInspectable**() const;
```

### <a name="remarks"></a>Hinweise

Wandelt das aktuelle [Ptr_](#ptr) Datenmembers, der einen Zeiger an eine-Zeiger-an die `IInspectable` Schnittstelle.

Ein Fehler wird ausgegeben, wenn die aktuelle `ComPtrRefBase` nicht abgeleitet `IInspectable`.

Diese Umwandlung ist verfügbar nur, wenn `__WRL_CLASSIC_COM__` definiert ist.

## <a name="operator-iunknown-star-star"></a>Comptrrefbase:: Operator IUnknown **

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
operator IUnknown**() const;
```

### <a name="remarks"></a>Hinweise

Wandelt das aktuelle [Ptr_](#ptr) Datenmembers, der einen Zeiger an eine-Zeiger-an die `IUnknown` Schnittstelle.

Ein Fehler wird ausgegeben, wenn die aktuelle `ComPtrRefBase` nicht abgeleitet `IUnknown`.

## <a name="ptr"></a>Comptrrefbase:: Ptr_

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
T* ptr_;
```

### <a name="remarks"></a>Hinweise

Zeiger auf den Typ, durch den aktuellen Vorlagenparameter angegeben. `ptr_` ist das Element für die geschützten Daten.
