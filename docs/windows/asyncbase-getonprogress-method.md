---
title: 'Asyncbase:: Getonprogress-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::GetOnProgress
dev_langs:
- C++
helpviewer_keywords:
- GetOnProgress method
ms.assetid: 286ddc9c-3e30-41a2-8e8b-e53d3fb0649d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5439e1c17b7ad654d44fad575ba51b9ebc4095bb
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592255"
---
# <a name="asyncbasegetonprogress-method"></a>AsyncBase::GetOnProgress-Methode

Kopiert die Adresse des aktuellen ereignishandlers Status an die angegebene Variable.

## <a name="syntax"></a>Syntax

```cpp
STDMETHOD(
   GetOnProgress
)(TProgress** progressHandler);
```

### <a name="parameters"></a>Parameter

*progressHandler*  
Der Speicherort, in dem die Adresse des aktuellen ereignishandlers Status gespeichert wird.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls E_ILLEGAL_METHOD_CALL.

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[AsyncBase-Klasse](../windows/asyncbase-class.md)