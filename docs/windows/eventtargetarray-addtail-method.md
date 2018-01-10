---
title: 'Eventtargetarray:: Addtail-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::Details::EventTargetArray::AddTail
dev_langs: C++
helpviewer_keywords: AddTail method
ms.assetid: d0fafab9-049c-40e0-a40c-d126c9ee63e6
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2ff008a60831ccce9a93bc3b4c4df8643db9c541
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="eventtargetarrayaddtail-method"></a>EventTargetArray::AddTail-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
void AddTail(  
   _In_ IUnknown* element  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `element`  
 Zeiger auf der Ereignishandler angefügt werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Fügt den angegebenen Ereignishandler an das Ende des internen Arrays von Ereignishandlern an.  
  
 AddTail() soll von EventSource-Klasse intern verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [EventTargetArray-Klasse](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)