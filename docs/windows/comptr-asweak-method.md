---
title: 'Comptr:: Asweak-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::AsWeak
dev_langs:
- C++
helpviewer_keywords:
- AsWeak method
ms.assetid: 23e29dcd-39cb-423f-abe6-6df4428213bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9f262191304471a171e9c3370046dbdac71869cd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33870076"
---
# <a name="comptrasweak-method"></a>ComPtr::AsWeak-Methode
Ruft einen schwachen Verweis (WeakReference) auf das aktuelle Objekt ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT AsWeak(  
   _Out_ WeakRef* pWeakRef  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pWeakRef`  
 Wenn dieser Vorgang abgeschlossen wird, einen Zeiger auf einen schwachen Verweis-Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtr-Klasse](../windows/comptr-class.md)