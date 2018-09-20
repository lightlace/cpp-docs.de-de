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
ms.openlocfilehash: 9a73608bd2faa8de2c5e23eff84290e7dd5fae11
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417188"
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

[WeakReference-Klasse](../windows/weakreference-class1.md)<br/>
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)