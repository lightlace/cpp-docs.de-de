---
title: 'Runtimeclass:: Getweakreference-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetWeakReference
dev_langs:
- C++
helpviewer_keywords:
- GetWeakReference method
ms.assetid: 26656ace-7f20-4364-87c9-4a75dd30912e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e49703e96728e7287206aa264ce12deaad611495
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33888216"
---
# <a name="runtimeclassgetweakreference-method"></a>RuntimeClass::GetWeakReference-Methode
Ruft einen Zeiger auf das Objekt schwachen Verweis für das aktuelle RuntimeClass-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHOD(  
   GetWeakReference  
)(_Deref_out_ IWeakReference **weakReference);  
```  
  
#### <a name="parameters"></a>Parameter  
 `weakReference`  
 Wenn dieser Vorgang abgeschlossen wird, einen Zeiger auf einen schwachen Verweis-Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Stets S_OK.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [RuntimeClass-Klasse](../windows/runtimeclass-class.md)