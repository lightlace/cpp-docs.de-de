---
title: InterfaceList-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceList
helpviewer_keywords:
- InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
ms.openlocfilehash: 70565081338f953abb65d2cdc7c5f1eb869f75e5
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54337437"
---
# <a name="interfacelist-structure"></a>InterfaceList-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <typename T, typename U>
struct InterfaceList;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Schnittstellenname einer; die erste Schnittstelle in der Liste rekursiv.

*U*<br/>
Der Schnittstellenname einer; die verbleibenden Schnittstellen in der Liste rekursiv.

## <a name="remarks"></a>Hinweise

Verwendet, um eine rekursive Liste von Schnittstellen erstellen.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`FirstT`|Synonym für den Vorlagenparameter *T*.|
|`RestT`|Synonym für den Vorlagenparameter *U*.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`InterfaceList`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](microsoft-wrl-details-namespace.md)