---
title: InterfaceList-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceList
helpviewer_keywords:
- InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
ms.openlocfilehash: 745348e81888b5a87c57fbb99d397fcd423c3ee1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398211"
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