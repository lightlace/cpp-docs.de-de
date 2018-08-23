---
title: 'Asyncbase:: Start-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Start
dev_langs:
- C++
helpviewer_keywords:
- Start method
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d81a3f29e99f49b03eb76f44af60c42d433e0bdc
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611231"
---
# <a name="asyncbasestart-method"></a>AsyncBase::Start-Methode

Beginnt den asynchronen Vorgang an.

## <a name="syntax"></a>Syntax

```cpp
STDMETHOD(
   Start
)(void);
```

## <a name="return-value"></a>Rückgabewert

S_OK, wenn der Vorgang gestartet oder bereits gestartet. andernfalls E_ILLEGAL_STATE_CHANGE.

## <a name="remarks"></a>Hinweise

**Start()** ist eine Standardimplementierung der `IAsyncInfo::Start`, und keine Arbeit erledigt. Um einen asynchronen Vorgang tatsächlich zu starten, überschreiben die `OnStart()` rein virtuelle Methode.

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[AsyncBase-Klasse](../windows/asyncbase-class.md)