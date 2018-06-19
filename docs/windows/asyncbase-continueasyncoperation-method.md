---
title: 'Asyncbase:: Continueasyncoperation-Methode | Microsoft Docs'
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
ms.openlocfilehash: caf7cd1cbee97761c6877ec6ab3a51ea956cbfd1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859591"
---
# <a name="asyncbasecontinueasyncoperation-method"></a>AsyncBase::ContinueAsyncOperation-Methode
Bestimmt, ob der asynchrone Vorgang der Verarbeitung fortsetzen oder Anhalten sollte.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline bool ContinueAsyncOperation();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Wenn der aktuelle Status des asynchronen Vorgangs ist *gestartet*, was bedeutet, dass den Vorgang fortgesetzt werden sollte. Andernfalls `false`, was bedeutet, dass den Vorgang sollte beendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)