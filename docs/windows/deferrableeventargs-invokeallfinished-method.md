---
title: 'Deferrableeventargs:: Invokeallfinished-Methode | Microsoft-Dokumentation'
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
ms.openlocfilehash: 23d521b8373969abdd739b6e4f48eb334284664d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605172"
---
# <a name="deferrableeventargsinvokeallfinished-method"></a>DeferrableEventArgs::InvokeAllFinished-Methode
Wird aufgerufen, um anzugeben, dass das Behandeln eines zurückgestellten Ereignisses abgeschlossen ist.
  
## <a name="syntax"></a>Syntax
  
```cpp
void InvokeAllFinished()  
```
  
## <a name="remarks"></a>Hinweise
 Sie sollten diese Methode aufrufen, nach dem Aufrufen der Quelle Ereignis [InvokeAll](../windows/eventsource-invokeall-method.md). Das Aufrufen dieser Methode verhindert weitere Verzögerungen und erzwingt die Ausführung des Abschlusshandlers, wenn keine Verzögerungen ausgeführt wurden.
  
 Ein Codebeispiel finden Sie unter [DeferrableEventArgs-Klasse](../windows/deferrableeventargs-class.md).
  
## <a name="requirements"></a>Anforderungen
 **Header:** event.h
  
 **Namespace:** Microsoft::WRL
  
## <a name="see-also"></a>Siehe auch
 [DeferrableEventArgs-Klasse](../windows/deferrableeventargs-class.md)  
 [EventSource::InvokeAll-Methode](../windows/eventsource-invokeall-method.md)