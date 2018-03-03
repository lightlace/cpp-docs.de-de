---
title: 'Asyncbase:: Continueasyncoperation-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation
dev_langs:
- C++
helpviewer_keywords:
- ContinueAsyncOperation method
ms.assetid: ce38181d-2fc3-4579-b0ce-237a3c7648bc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7e86c4857aab7c0e1a23dcd03695d906a3d9e5e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasecontinueasyncoperation-method"></a>AsyncBase::ContinueAsyncOperation-Methode
Bestimmt, ob der asynchrone Vorgang der Verarbeitung fortsetzen oder Anhalten sollte.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline bool ContinueAsyncOperation();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 `true`Wenn der aktuelle Status des asynchronen Vorgangs ist *gestartet*, was bedeutet, dass den Vorgang fortgesetzt werden sollte. Andernfalls `false`, was bedeutet, dass den Vorgang sollte beendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)