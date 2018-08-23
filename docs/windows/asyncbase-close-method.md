---
title: 'Asyncbase:: Close-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: a52b1124-754b-4393-b491-64aae0c22f1c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 732eb6f8668f7742e23e1ea410dcc659bc3d36c7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605345"
---
# <a name="asyncbaseclose-method"></a>AsyncBase::Close-Methode

Schließt den asynchronen Vorgang an.

## <a name="syntax"></a>Syntax

```cpp
STDMETHOD(
   Close
)(void) override;
```

## <a name="return-value"></a>Rückgabewert

S_OK, wenn der Vorgang geschlossen oder bereits ist geschlossen wurde, andernfalls E_ILLEGAL_STATE_CHANGE.

## <a name="remarks"></a>Hinweise

**Close()** ist eine Standardimplementierung der `IAsyncInfo::Close`, und keine Arbeit erledigt. Um einen asynchronen Vorgang tatsächlich zu schließen, außer Kraft setzen der `OnClose()` rein virtuelle Methode.

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[AsyncBase-Klasse](../windows/asyncbase-class.md)