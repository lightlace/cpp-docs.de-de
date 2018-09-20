---
title: 'Asyncbase:: currentStatus-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::CurrentStatus
dev_langs:
- C++
helpviewer_keywords:
- CurrentStatus method
ms.assetid: 26ee4c4a-6525-4a5f-b49c-3ca40c365eb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 792f9f6c6d76097459498c43068f46d86b2e2349
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401484"
---
# <a name="asyncbasecurrentstatus-method"></a>AsyncBase::CurrentStatus-Methode

Ruft den Status der aktuellen asynchronen Vorgang ab.

## <a name="syntax"></a>Syntax

```cpp
inline void CurrentStatus(
   Details::AsyncStatusInternal *status
);
```

### <a name="parameters"></a>Parameter

*status*<br/>
Der Speicherort, in dem dieser Vorgang für den aktuellen Status speichert.

## <a name="remarks"></a>Hinweise

Dieser Vorgang ist threadsicher.

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[AsyncBase-Klasse](../windows/asyncbase-class.md)<br/>
[AsyncStatusInternal-Enumeration](../windows/asyncstatusinternal-enumeration.md)