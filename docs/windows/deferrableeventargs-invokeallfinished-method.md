---
title: 'Deferrableeventargs:: Invokeallfinished-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 86b45205-3edb-4134-9cd0-ed7a7b4c3b1a
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: acae8467ceeaaafea6668d4fbf6b5e2f4884b373
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="deferrableeventargsinvokeallfinished-method"></a>DeferrableEventArgs::InvokeAllFinished-Methode
Wird aufgerufen, um anzugeben, dass das Behandeln eines zurückgestellten Ereignisses abgeschlossen ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void InvokeAllFinished()  
```  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode nach dem Aufrufen der Quelle Ereignis [InvokeAll](../windows/eventsource-invokeall-method.md). Das Aufrufen dieser Methode verhindert weitere Verzögerungen und erzwingt die Ausführung des Abschlusshandlers, wenn keine Verzögerungen ausgeführt wurden.  
  
 Ein Codebeispiel finden Sie unter [DeferrableEventArgs-Klasse](../windows/deferrableeventargs-class.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [DeferrableEventArgs-Klasse](../windows/deferrableeventargs-class.md)   
 [EventSource::InvokeAll-Methode](../windows/eventsource-invokeall-method.md)