---
title: 'Asyncbase:: Trytransitiontoerror-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
dev_langs:
- C++
helpviewer_keywords:
- TryTransitionToError method
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fc677304ae7ab61e6726366869e85f731cd92484
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463206"
---
# <a name="asyncbasetrytransitiontoerror-method"></a>AsyncBase::TryTransitionToError-Methode
Gibt an, ob der angegebene Fehlercode auf den internen Fehlerzustand ändern kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
bool TryTransitionToError(  
   const HRESULT error  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *Fehler*  
 Ein fehlerhaftes HRESULT.  
  
## <a name="return-value"></a>Rückgabewert  
 **"true"** bei der internen Fehlerzustand geändert wurde, andernfalls **"false"**.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Vorgang ändert den Status "Fehler" nur dann, wenn der Status "Fehler" S_OK bereits festgelegt ist. Dieser Vorgang hat keine Auswirkungen, wenn der Status "Fehler" bereits angezeigt wird, abgeschlossen, abgebrochen oder geschlossen ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)