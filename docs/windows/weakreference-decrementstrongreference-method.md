---
title: 'WeakReference:: Decrementstrongreference-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference
dev_langs:
- C++
helpviewer_keywords:
- DecrementStrongReference method
ms.assetid: 97d70d9f-41b8-4f8d-a6fa-4137cc4f9029
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b3620a4b82aabb0058773f68938f545119f90791
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605597"
---
# <a name="weakreferencedecrementstrongreference-method"></a>WeakReference::DecrementStrongReference-Methode

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
ULONG DecrementStrongReference();
```

## <a name="remarks"></a>Hinweise

Dekrementiert den starken Verweiszähler des aktuellen **WeakReference** Objekt.

Die Anzahl der starken Verweis auf 0 (null) ist, wird der starke Verweis als festgelegt **"nullptr"**.

## <a name="return-value"></a>Rückgabewert

Die Anzahl verringert starken Verweis.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[WeakReference-Klasse](../windows/weakreference-class1.md)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)