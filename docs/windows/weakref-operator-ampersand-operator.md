---
title: Weakref::&amp; Operator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::operator&
dev_langs:
- C++
helpviewer_keywords:
- operator& operator
ms.assetid: 900afb73-3801-4d08-9b41-2e6a62011ccd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f8bb81ca1591fc398b1d0814fca918309169e82c
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600983"
---
# <a name="weakrefoperatoramp-operator"></a>Weakref::&amp; Operator

Gibt eine `ComPtrRef` -Objekt, das der aktuelle darstellt **WeakRef** Objekt.

## <a name="syntax"></a>Syntax

```cpp
Details::ComPtrRef<WeakRef> operator&() throw()  
```

## <a name="return-value"></a>Rückgabewert

Ein `ComPtrRef` -Objekt, das der aktuelle darstellt **WeakRef** Objekt.

## <a name="remarks"></a>Hinweise

Dies ist eine interne Hilfsmethode-Operator, der nicht in Ihrem Code verwendet werden soll.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[WeakRef-Klasse](../windows/weakref-class.md)