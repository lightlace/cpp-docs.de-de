---
title: 'Asyncbase:: Start-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::Start
dev_langs: C++
helpviewer_keywords: Start method
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 419cbec3500977ec5dbeb063e444c1fced8783aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasestart-method"></a>AsyncBase::Start-Methode
Beginnt den asynchronen Vorgang an.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHOD(  
   Start  
)(void);  
```  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn der Vorgang gestartet wird oder bereits gestartet. andernfalls E_ILLEGAL_STATE_CHANGE.  
  
## <a name="remarks"></a>Hinweise  
 Start() ist eine Standardimplementierung von IAsyncInfo::Start und keine tatsächliche Arbeit ausführt. Um einen asynchronen Vorgang tatsächlich zu starten, überschreiben Sie die OnStart() reine virtuelle Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)