---
title: 'EventSource:: InvokeAll-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::InvokeAll
dev_langs:
- C++
helpviewer_keywords:
- InvokeAll method
ms.assetid: 1506618f-0421-4428-a4d0-4ea2b10a3bf6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9ea378f75f100bce02cd486139fb0aac5ea5a5ff
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648632"
---
# <a name="eventsourceinvokeall-method"></a>EventSource::InvokeAll-Methode
Ruft jede Ereignishandler verknüpft ist, mit dem aktuellen [EventSource](../windows/eventsource-class.md) -Objekt mit den angegebenen Argumenttypen und der Argumente.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void InvokeAll();  
template <  
   typename T0  
>  
void InvokeAll(  
   T0arg0  
);  
template <  
   typename T0,  
   typename T1  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6,  
   typename T7  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6,  
   T7arg7  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6,  
   typename T7,  
   typename T8  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6,  
   T7arg7,  
   T8arg8  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6,  
   typename T7,  
   typename T8,  
   typename T9  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6,  
   T7arg7,  
   T8arg8,  
   T9arg9  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *T0*  
 Der Typ des Arguments nullten Event Handler.  
  
 *T1*  
 Der Typ, der das erste Argument der Ereignis-Handler.  
  
 *T2*  
 Der Typ des zweiten Arguments der Ereignis-Handler.  
  
 *T3*  
 Der Typ des dritten Arguments der Ereignis-Handler.  
  
 *T4*  
 Der Typ des vierten Arguments der Ereignis-Handler.  
  
 *T5*  
 Der Typ des fünften Arguments der Ereignis-Handler.  
  
 *T6*  
 Der Typ des sechsten Arguments der Ereignis-Handler.  
  
 *T7*  
 Der Typ des siebten Arguments der Ereignis-Handler.  
  
 *T8*  
 Der Typ des Arguments achte Event Handler.  
  
 *T9*  
 Der Typ des neunten Arguments der Ereignis-Handler.  
  
 *arg0*  
 Das Argument der nullten Ereignis-Handler.  
  
 *arg1*  
 Das erste Argument der Ereignis-Handler.  
  
 *Arg2*  
 Das zweite Argument der Ereignis-Handler.  
  
 *Arg3*  
 Das dritte Argument der Ereignis-Handler.  
  
 *Arg4*  
 Das vierte Argument der Ereignis-Handler.  
  
 *Arg5*  
 Das fünfte Argument der Ereignis-Handler.  
  
 *Arg6*  
 Das sechste Handler Ereignisargument.  
  
 *Arg7*  
 Das siebte Handler Ereignisargument.  
  
 *Arg8*  
 Das achte Handler Ereignisargument.  
  
 *Arg9*  
 Das neunte Handler Ereignisargument.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [EventSource-Klasse](../windows/eventsource-class.md)