---
title: 'Asyncbase:: Continueasyncoperation-Methode | Microsoft-Dokumentation'
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
ms.openlocfilehash: e7b5d2b10b571a3517beab98eaa839d5c7fd86c2
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39460832"
---
# <a name="asyncbasecontinueasyncoperation-method"></a>AsyncBase::ContinueAsyncOperation-Methode
Bestimmt, ob der asynchrone Vorgang im Fortsetzen der Verarbeitung oder anhalten soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline bool ContinueAsyncOperation();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 **"true"** ist von der aktuelle Status des asynchronen Vorgangs *Schritte*, was bedeutet, dass den Vorgang sollte weiterhin. Andernfalls **"false"**, was bedeutet, dass den Vorgang sollte beendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)