---
title: CompareStringOrdinal-Methode | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
dev_langs:
- C++
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0dc85bad774260f3db589d4f2649e0c39de2a530
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067201"
---
# <a name="comparestringordinal-method"></a>CompareStringOrdinal-Methode

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
inline INT32 CompareStringOrdinal(
   HSTRING lhs,
   HSTRING rhs)
```

### <a name="parameters"></a>Parameter

*LHS*<br/>
Das erste HSTRING, verglichen werden soll.

*RS*<br/>
Das zweite HSTRING, verglichen werden soll.

## <a name="return-value"></a>Rückgabewert

|Wert|Bedingung|
|-----------|---------------|
|-1|*LHS* ist kleiner als *RS*.|
|0|*LHS* gleich *RS*.|
|1|*LHS* ist größer als *RS*.|

## <a name="remarks"></a>Hinweise

Vergleicht zwei angegebene HSTRING-Objekte und gibt eine ganze Zahl, die ihre relative Position in einer Sortierreihenfolge angibt.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Wrappers::Details-Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)