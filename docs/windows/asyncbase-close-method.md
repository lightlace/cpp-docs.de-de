---
title: 'Asyncbase:: Close-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: a52b1124-754b-4393-b491-64aae0c22f1c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4f3f36656b9316fb6ad980349a836fad31c3a9a0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="asyncbaseclose-method"></a>AsyncBase::Close-Methode
Schließt den asynchronen Vorgang an.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHOD(  
   Close  
)(void) override;  
```  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn der Vorgang geschlossen wird oder bereits geschlossen. andernfalls E_ILLEGAL_STATE_CHANGE.  
  
## <a name="remarks"></a>Hinweise  
 Close() eine Standardimplementierung von IAsyncInfo::Close ist und keine tatsächliche Arbeit ausführt. Außer Kraft setzen Sie die OnClose() reine virtuelle Methode, um einen asynchronen Vorgang tatsächlich zu schließen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)