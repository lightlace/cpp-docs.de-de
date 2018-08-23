---
title: 'Asyncbase:: Continueasyncoperation-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation
dev_langs:
- C++
helpviewer_keywords:
- ContinueAsyncOperation method
ms.assetid: ce38181d-2fc3-4579-b0ce-237a3c7648bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b83d7a0bb5eadede42d2572d5ebc5a02a0fe9a0e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607184"
---
# <a name="asyncbasecontinueasyncoperation-method"></a>AsyncBase::ContinueAsyncOperation-Methode

Bestimmt, ob der asynchrone Vorgang im Fortsetzen der Verarbeitung oder anhalten soll.

## <a name="syntax"></a>Syntax

```cpp
inline bool ContinueAsyncOperation();
```

## <a name="return-value"></a>Rückgabewert

**"true"** ist von der aktuelle Status des asynchronen Vorgangs *Schritte*, was bedeutet, dass den Vorgang sollte weiterhin. Andernfalls **"false"**, was bedeutet, dass den Vorgang sollte beendet werden.

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[AsyncBase-Klasse](../windows/asyncbase-class.md)