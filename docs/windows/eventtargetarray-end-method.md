---
title: 'Eventtargetarray:: End-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::Details::EventTargetArray::End
dev_langs: C++
helpviewer_keywords: End method
ms.assetid: 20c491b8-f355-4d8f-ad14-8f46121d9af6
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5bb10bf3d88f9c6f0615501a899d60b4a184405c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="eventtargetarrayend-method"></a>EventTargetArray::End-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
ComPtr<IUnknown>* End();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Die Adresse des letzten Elements im internen Array von Ereignishandlern.  
  
## <a name="remarks"></a>Hinweise  
 Ruft die Adresse des letzten Elements im internen Array von Ereignishandlern.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [EventTargetArray-Klasse](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)