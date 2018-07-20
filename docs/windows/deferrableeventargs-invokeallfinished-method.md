---
title: 'Deferrableeventargs:: Invokeallfinished-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 86b45205-3edb-4134-9cd0-ed7a7b4c3b1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1aaaf8c6849b30e26463810ff353234319960048
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883367"
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