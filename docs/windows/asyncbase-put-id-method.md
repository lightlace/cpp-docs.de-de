---
title: 'Asyncbase:: Put_id-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::put_Id
dev_langs:
- C++
helpviewer_keywords:
- put_Id method
ms.assetid: aebad85f-4774-42de-b625-a9cf5f65cb4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 65d36c76ca05343084b709096d38014d802628c8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439002"
---
# <a name="asyncbaseputid-method"></a>AsyncBase::put_Id-Methode

Legt das Handle des asynchronen Vorgangs fest.

## <a name="syntax"></a>Syntax

```cpp
STDMETHOD(
   put_Id
)(const unsigned int id);
```

### <a name="parameters"></a>Parameter

*ID*<br/>
Ein ungleich NULL-Handle.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls E_INVALIDARG oder E_ILLEGAL_METHOD_CALL.

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[AsyncBase-Klasse](../windows/asyncbase-class.md)