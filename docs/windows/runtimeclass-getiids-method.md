---
title: 'Runtimeclass:: Getiids-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetIids
dev_langs:
- C++
helpviewer_keywords:
- GetIids method
ms.assetid: 826a67d1-ebc4-4940-b5d5-7cd66885e4a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c309c97b9c9ce057ca67ab4b5d729c61d803ea5a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33888401"
---
# <a name="runtimeclassgetiids-method"></a>RuntimeClass::GetIids-Methode
Ruft ein Array, die die Schnittstelle IDs vom aktuellen RuntimeClass-Objekt implementiert enthalten kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHOD(  
   GetIids  
)  
   (_Out_ ULONG *iidCount,   
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
#### <a name="parameters"></a>Parameter  
 `iidCount`  
 Wenn dieser Vorgang abgeschlossen ist, die Gesamtanzahl der Elemente im Array `iids`.  
  
 `iids`  
 Wenn dieser Vorgang abgeschlossen wird, einen Zeiger auf ein Array von Schnittstellen-IDs.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls E_OUTOFMEMORY.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [RuntimeClass-Klasse](../windows/runtimeclass-class.md)