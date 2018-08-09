---
title: 'Asyncbase:: Cancel-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Cancel
dev_langs:
- C++
helpviewer_keywords:
- Cancel method
ms.assetid: 8bfebc63-3848-4629-bc89-aa538ed7e7ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 439a118bbea5adce4c306298e573bed85da26291
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641903"
---
# <a name="asyncbasecancel-method"></a>AsyncBase::Cancel-Methode
Bricht einen asynchronen Vorgang ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
STDMETHOD(  
   Cancel  
)(void);  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Standardmäßig gibt stets S_OK zurück.  
  
## <a name="remarks"></a>Hinweise  
 **Cancel()** ist eine Standardimplementierung der `IAsyncInfo::Cancel`, und keine Arbeit erledigt. Um einen asynchronen Vorgang tatsächlich abgebrochen werden soll, überschreiben die `OnCancel()` rein virtuelle Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)