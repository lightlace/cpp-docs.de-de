---
title: 'Asyncbase:: Cancel-Methode | Microsoft Docs'
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
ms.openlocfilehash: 0559f32315265a7db5543e8559097177c2a670fa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859851"
---
# <a name="asyncbasecancel-method"></a>AsyncBase::Cancel-Methode
Bricht einen asynchronen Vorgang ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHOD(  
   Cancel  
)(void);  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Standardmäßig gibt stets S_OK zurück.  
  
## <a name="remarks"></a>Hinweise  
 Cancel() wird eine Standardimplementierung von IAsyncInfo::Cancel ist und keine tatsächliche Arbeit ausführt. Um einen asynchronen Vorgang tatsächlich "Abbrechen", überschreiben Sie die OnCancel() reine virtuelle Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)