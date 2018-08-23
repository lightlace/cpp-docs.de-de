---
title: 'Asyncbase:: Putonprogress-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::PutOnProgress
dev_langs:
- C++
helpviewer_keywords:
- PutOnProgress method
ms.assetid: 1f5f180e-eb5a-4afe-ac16-69dbf36f0383
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8b2bc46f916e4aaaedc74e8b6d94faafa1ead3b9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595486"
---
# <a name="asyncbaseputonprogress-method"></a>AsyncBase::PutOnProgress-Methode

Legt die Adresse des ereignishandlers Status mit dem angegebenen Wert fest.

## <a name="syntax"></a>Syntax

```cpp
STDMETHOD(
   PutOnProgress
)(TProgress* progressHandler);
```

### <a name="parameters"></a>Parameter

*progressHandler*  
Die Adresse, die auf der der Status-Ereignishandler festgelegt ist.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls E_ILLEGAL_METHOD_CALL.

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[AsyncBase-Klasse](../windows/asyncbase-class.md)