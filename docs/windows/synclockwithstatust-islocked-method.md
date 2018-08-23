---
title: 'Synclockwithstatust:: IsLocked-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
dev_langs:
- C++
helpviewer_keywords:
- IsLocked method
ms.assetid: e1b75b7b-c145-471a-aa5d-71abf31f5990
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d70a2c316f9e7994292f3dc29cef5bce993778ad
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595062"
---
# <a name="synclockwithstatustislocked-method"></a>SyncLockWithStatusT::IsLocked-Methode

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
bool IsLocked() const;
```

## <a name="remarks"></a>Hinweise

Gibt an, ob die aktuelle **SyncLockWithStatusT** Objekt besitzt eine Ressource, d. h. die **SyncLockWithStatusT** Objekt *gesperrt*.

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn die **SyncLockWithStatusT** Objekt gesperrt ist; andernfalls **"false"**.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>Siehe auch

[SyncLockWithStatusT-Klasse](../windows/synclockwithstatust-class.md)