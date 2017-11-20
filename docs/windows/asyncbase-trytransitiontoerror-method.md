---
title: 'Asyncbase:: Trytransitiontoerror-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::TryTransitionToError
dev_langs: C++
helpviewer_keywords: TryTransitionToError method
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 04019cc27866c41f263f7d51fa6b5ae0cfd9e000
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbasetrytransitiontoerror-method"></a>AsyncBase::TryTransitionToError-Methode
Gibt an, ob der angegebene Fehlercode Zustand "Interner Fehler" ändern kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
bool TryTransitionToError(  
   const HRESULT error  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `error`  
 Ein Fehler-HRESULT.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Zustand "Interner Fehler" geändert wurde. andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Vorgang ändert den Status "Fehler" nur, wenn der Status "Fehler" bereits mit S_OK festgelegt ist. Dieser Vorgang hat keine Auswirkung, wenn der Status "Fehler" bereits angezeigt wird, abgeschlossen, abgebrochen oder geschlossen ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)