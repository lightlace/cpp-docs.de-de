---
title: 'Synclockt:: IsLocked-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked
dev_langs:
- C++
helpviewer_keywords:
- IsLocked method
ms.assetid: a81fea43-f99a-4708-812a-7fd6af500d3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ca4391539e4f6987431e8b9b036053db02218007
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593054"
---
# <a name="synclocktislocked-method"></a>SyncLockT::IsLocked-Methode

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
bool IsLocked() const;
```

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn die **SyncLockT** Objekt gesperrt ist; andernfalls **"false"**.

## <a name="remarks"></a>Hinweise

Gibt an, ob die aktuelle **SyncLockT** Objekt besitzt eine Ressource, d. h. die **SyncLockT** Objekt *gesperrt*.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>Siehe auch

[SyncLockT-Klasse](../windows/synclockt-class.md)