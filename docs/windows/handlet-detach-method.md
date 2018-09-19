---
title: 'Handlet:: Detach-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: f7df0f90-fafb-4d1b-a215-a6c62941f6b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b66d5c65dd084da564067cd62242b315f6da182
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591373"
---
# <a name="handletdetach-method"></a>HandleT::Detach-Methode

Hebt die Zuordnung der aktuellen **HandleT** Objekt aus der zugrunde liegende Handle.

## <a name="syntax"></a>Syntax

```cpp
typename HandleTraits::Type Detach();
```

## <a name="return-value"></a>Rückgabewert

Das zugrunde liegende Handle.

## <a name="remarks"></a>Hinweise

Wenn dieser Vorgang abgeschlossen ist, die aktuelle **HandleT** auf einen ungültigen Zustand festgelegt ist.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HandleT-Klasse](../windows/handlet-class.md)