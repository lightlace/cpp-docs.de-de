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
ms.openlocfilehash: 193f4d26f7e163707092f3d0bc8f981a02611a22
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603701"
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

*status*  
Der Speicherort, in dem dieser Vorgang für den aktuellen Status speichert.

## <a name="remarks"></a>Hinweise

Dieser Vorgang ist threadsicher.

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[AsyncBase-Klasse](../windows/asyncbase-class.md)  
[AsyncStatusInternal-Enumeration](../windows/asyncstatusinternal-enumeration.md)