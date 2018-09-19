---
title: 'Asyncbase:: Putoncomplete-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::PutOnComplete
dev_langs:
- C++
helpviewer_keywords:
- PutOnComplete method
ms.assetid: 1c469ff9-b2df-4637-bf05-01a617043149
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c62119b87183fe6a60c0ed4d987cbd12788d8a0d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602685"
---
# <a name="asyncbaseputoncomplete-method"></a>AsyncBase::PutOnComplete-Methode

Legt die Adresse des ereignishandlers Abschluss auf den angegebenen Wert fest.

## <a name="syntax"></a>Syntax

```cpp
STDMETHOD(
   PutOnComplete
)(TComplete* completeHandler);
```

### <a name="parameters"></a>Parameter

*completeHandler*  
Die Adresse, die auf die der Abschluss-Ereignishandler festgelegt ist.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls E_ILLEGAL_METHOD_CALL.

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[AsyncBase-Klasse](../windows/asyncbase-class.md)