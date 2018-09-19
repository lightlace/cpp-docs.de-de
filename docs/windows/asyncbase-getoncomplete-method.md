---
title: 'Asyncbase:: Getoncomplete-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::GetOnComplete
dev_langs:
- C++
helpviewer_keywords:
- GetOnComplete method
ms.assetid: f06ae02d-9a88-41d2-b749-bdc1a7ff8748
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eab2a577d0c7b31f833a8dcc0208f9939b729ad9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607468"
---
# <a name="asyncbasegetoncomplete-method"></a>AsyncBase::GetOnComplete-Methode

Kopiert die Adresse des aktuellen ereignishandlers Abschluss an die angegebene Variable.

## <a name="syntax"></a>Syntax

```cpp
STDMETHOD(
   GetOnComplete
)(TComplete** completeHandler);
```

### <a name="parameters"></a>Parameter

*completeHandler*  
Der Speicherort, in dem die Adresse des aktuellen ereignishandlers Abschluss gespeichert ist.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls E_ILLEGAL_METHOD_CALL.

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[AsyncBase-Klasse](../windows/asyncbase-class.md)