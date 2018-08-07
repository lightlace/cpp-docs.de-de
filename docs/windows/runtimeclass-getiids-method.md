---
title: 'Runtimeclass:: Getiids-Methode | Microsoft-Dokumentation'
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
ms.openlocfilehash: 87f51d39bf1ff8c7d4271797dcaa23278ac2e747
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608442"
---
# <a name="runtimeclassgetiids-method"></a>RuntimeClass::GetIids-Methode
Ruft ein Array, das die Schnittstellen-IDs, die von der aktuellen Implementierung darf **RuntimeClass** Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHOD(  
   GetIids  
)  
   (_Out_ ULONG *iidCount,   
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
### <a name="parameters"></a>Parameter  
 *iidCount*  
 Wenn dieser Vorgang abgeschlossen ist, die Gesamtzahl der Elemente im Array *Iids*.  
  
 *IIDs*  
 Wenn dieser Vorgang abgeschlossen ist, einen Zeiger auf ein Array von Schnittstellen-IDs.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls E_OUTOFMEMORY.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [RuntimeClass-Klasse](../windows/runtimeclass-class.md)