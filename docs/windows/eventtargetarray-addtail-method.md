---
title: 'Eventtargetarray:: Addtail-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::AddTail
dev_langs:
- C++
helpviewer_keywords:
- AddTail method
ms.assetid: d0fafab9-049c-40e0-a40c-d126c9ee63e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b469adedebda2beb64c531c82d10f90cc4114742
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570173"
---
# <a name="eventtargetarrayaddtail-method"></a>EventTargetArray::AddTail-Methode
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
void AddTail(  
   _In_ IUnknown* element  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *Element*  
 Zeiger auf den Ereignishandler, angefügt werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Fügt den angegebenen Ereignishandler an das Ende des internen Arrays von Ereignishandlern an.  
  
 **AddTail()** soll nur intern von verwendet werden. die `EventSource` Klasse.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [EventTargetArray-Klasse](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)