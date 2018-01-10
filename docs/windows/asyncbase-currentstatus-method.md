---
title: 'Asyncbase:: currentStatus-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::CurrentStatus
dev_langs: C++
helpviewer_keywords: CurrentStatus method
ms.assetid: 26ee4c4a-6525-4a5f-b49c-3ca40c365eb6
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c72e66a179e47e890cbe90da7a3e54afa41ce942
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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