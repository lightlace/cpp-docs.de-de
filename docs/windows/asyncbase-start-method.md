---
title: 'Asyncbase:: Start-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Start
dev_langs:
- C++
helpviewer_keywords:
- Start method
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0acc6f62530daf641a2e4d568ed511d6fd831c20
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860917"
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