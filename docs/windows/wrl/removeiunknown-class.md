---
title: RemoveIUnknown-Klasse
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
ms.openlocfilehash: bfe397f64650caedab1408f1f74fabd005dd98cf
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336093"
---
# <a name="removeiunknown-class"></a>RemoveIUnknown-Klasse

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <typename T>
struct RemoveIUnknown;

template <typename T>
class RemoveIUnknown : public T;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Eine Klasse.

## <a name="remarks"></a>Hinweise

Ist einen Typ, der entspricht einer `IUnknown`-Basis-Typ, weist jedoch nicht virtuelle `QueryInterface`, `AddRef`, und `Release` Memberfunktionen.

COM-Methoden in der Standardeinstellung bieten virtuelle `QueryInterface`, `AddRef`, und `Release` Methoden. Allerdings `ComPtr` erfordert nicht die Zusatzaufwand virtueller Methoden. `RemoveIUnknown` entfällt dieser Mehraufwand durch die Bereitstellung von privaten, nicht virtuelle `QueryInterface`, `AddRef`, und `Release` Methoden.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`ReturnType`|Ein Synonym für einen Typ, die Template-Parameter entspricht *T* aber nicht virtuelle `IUnknown` Member.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`T`

`RemoveIUnknown`

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](microsoft-wrl-details-namespace.md)