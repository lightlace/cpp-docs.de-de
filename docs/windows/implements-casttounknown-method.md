---
title: 'Implements:: casttounknown-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: ca3324f7-4136-406b-8698-7389f4f3d3c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 988580a34c030c84c50adfff2741408be4b249cd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42586357"
---
# <a name="implementscasttounknown-method"></a>Implements::CastToUnknown-Methode

Ruft einen Zeiger auf die zugrunde liegende `IUnknown` Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
__forceinline IUnknown* CastToUnknown();
```

## <a name="return-value"></a>Rückgabewert

Dieser Vorgang immer erfolgreich ist, und gibt die `IUnknown` Zeiger.

## <a name="remarks"></a>Hinweise

Interne Hilfsmethode-Funktion.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Implements-Struktur](../windows/implements-structure.md)