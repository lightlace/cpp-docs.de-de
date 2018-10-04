---
title: InterfaceList-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceList
dev_langs:
- C++
helpviewer_keywords:
- InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3d9cbc1dfb31d744086e7a138521ae24f58e693f
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788655"
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

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)