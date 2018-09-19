---
title: 'WeakReference:: Incrementstrongreference-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::IncrementStrongReference
dev_langs:
- C++
helpviewer_keywords:
- IncrementStrongReference method
ms.assetid: d0232426-a8cb-48b4-99d4-165de2d66cb9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a0c8e9ba093c6be4b1e0d5747c16a8dc8887cd2c
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591087"
---
# <a name="weakreferenceincrementstrongreference-method"></a>WeakReference::IncrementStrongReference-Methode

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
ULONG IncrementStrongReference();
```

## <a name="return-value"></a>Rückgabewert

Die Anzahl inkrementiert starken Verweis.

## <a name="remarks"></a>Hinweise

Inkrementiert die Anzahl der starken Verweis des aktuellen **WeakReference** Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[WeakReference-Klasse](../windows/weakreference-class1.md)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)