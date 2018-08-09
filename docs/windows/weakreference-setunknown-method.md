---
title: 'WeakReference:: Setunknown-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::SetUnknown
dev_langs:
- C++
helpviewer_keywords:
- SetUnknown method
ms.assetid: 5dddb9e3-a7c1-4195-8166-97c5ab6e972f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2a46db38bf17b1af5ae748cf90689509d6d21b0d
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647679"
---
# <a name="weakreferencesetunknown-method"></a>WeakReference::SetUnknown-Methode
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
void SetUnknown(  
   _In_ IUnknown* unk  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *UNK*  
 Ein Zeiger auf die `IUnknown` -Schnittstelle eines Objekts.  
  
## <a name="remarks"></a>Hinweise  
 Den starken Verweis des aktuellen legt **WeakReference** Objekt, das den angegebenen Schnittstellenzeiger auf.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch
 [WeakReference-Klasse](../windows/weakreference-class1.md)  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)