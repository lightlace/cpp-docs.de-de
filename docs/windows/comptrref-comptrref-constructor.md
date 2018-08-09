---
title: 'Comptrref:: Comptrref-Konstruktor | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::ComPtrRef
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRef, constructor
ms.assetid: ce2d2533-fef6-4b2d-b088-6f3db01df5a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 621f852728cb40ea88a916b37147c28d8bb0db38
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644461"
---
# <a name="comptrrefcomptrref-constructor"></a>ComPtrRef::ComPtrRef-Konstruktor
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
ComPtrRef(  
   _In_opt_ T* ptr  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *ptr*  
 Der zugrunde liegenden Wert eines anderen **ComPtrRef** Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Initialisiert eine neue Instanz der dem **ComPtrRef** Klasse aus dem angegebenen Zeiger auf einen anderen **ComPtrRef** Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtrRef-Klasse](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)