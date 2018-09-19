---
title: 'Asyncbase:: Checkvalidstateforresultscall-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall
dev_langs:
- C++
helpviewer_keywords:
- CheckValidStateForResultsCall method
ms.assetid: 87ca6805-bff1-4063-b855-6dd26132deff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 398f46d5f8eb15d961d80b9a7a20b758fffd09c3
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42584235"
---
# <a name="asyncbasecheckvalidstateforresultscall-method"></a>AsyncBase::CheckValidStateForResultsCall-Methode

Testet, ob die Ergebnisse eines asynchronen Vorgangs in den aktuellen asynchronen Zustand erfasst werden können.

## <a name="syntax"></a>Syntax

```cpp
inline HRESULT CheckValidStateForResultsCall();
```

## <a name="return-value"></a>Rückgabewert

S_OK, wenn Ergebnisse erfasst werden können; andernfalls E_ILLEGAL_METHOD_CALLE_ILLEGAL_METHOD_CALL.

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[AsyncBase-Klasse](../windows/asyncbase-class.md)