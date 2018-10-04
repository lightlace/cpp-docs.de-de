---
title: RemoveIUnknown-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
dev_langs:
- C++
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c13f84916bf4733d906a1bd50411a85c6a5ed1e0
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788954"
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

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)