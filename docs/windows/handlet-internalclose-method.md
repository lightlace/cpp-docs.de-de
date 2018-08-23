---
title: 'Handlet:: Internalclose-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
dev_langs:
- C++
helpviewer_keywords:
- InternalClose method
ms.assetid: fe693c02-aa1f-4e00-8bdd-a0d7d736da0b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fc3f01227cb37285f11ef8256d0b101f156871b5
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605515"
---
# <a name="handletinternalclose-method"></a>HandleT::InternalClose-Methode

Schließt das aktuelle **HandleT** Objekt.

## <a name="syntax"></a>Syntax

```cpp
virtual bool InternalClose();
```

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn die aktuelle **HandleT** geschlossen wird, erfolgreich ist; andernfalls **"false"**.

## <a name="remarks"></a>Hinweise

**InternalClose()** ist **geschützt**.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HandleT-Klasse](../windows/handlet-class.md)