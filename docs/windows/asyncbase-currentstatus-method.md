---
title: 'Asyncbase:: currentStatus-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::CurrentStatus
dev_langs:
- C++
helpviewer_keywords:
- CurrentStatus method
ms.assetid: 26ee4c4a-6525-4a5f-b49c-3ca40c365eb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 75b9a07fd88caa9db7f2f145069b0d8857b79fe9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859689"
---
# <a name="asyncbasecurrentstatus-method"></a>AsyncBase::CurrentStatus-Methode
Ruft den Status der aktuellen asynchronen Vorgang ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline void CurrentStatus(  
   Details::AsyncStatusInternal *status  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `status`  
 Der Speicherort, in dem dieser Vorgang für den aktuellen Status speichert.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Vorgang ist threadsicher.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)   
 [AsyncStatusInternal-Enumeration](../windows/asyncstatusinternal-enumeration.md)