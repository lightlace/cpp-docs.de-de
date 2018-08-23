---
title: 'Asyncbase:: Cancel-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Cancel
dev_langs:
- C++
helpviewer_keywords:
- Cancel method
ms.assetid: 8bfebc63-3848-4629-bc89-aa538ed7e7ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dbf216d672dd22e453f8c213f7a9f34f08a47273
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593136"
---
# <a name="asyncbasecancel-method"></a>AsyncBase::Cancel-Methode

Bricht einen asynchronen Vorgang ab.

## <a name="syntax"></a>Syntax

```cpp
STDMETHOD(
   Cancel
)(void);
```

## <a name="return-value"></a>Rückgabewert

Standardmäßig gibt stets S_OK zurück.

## <a name="remarks"></a>Hinweise

**Cancel()** ist eine Standardimplementierung der `IAsyncInfo::Cancel`, und keine Arbeit erledigt. Um einen asynchronen Vorgang tatsächlich abgebrochen werden soll, überschreiben die `OnCancel()` rein virtuelle Methode.

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[AsyncBase-Klasse](../windows/asyncbase-class.md)