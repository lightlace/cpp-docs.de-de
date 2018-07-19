---
title: 'EventSource:: InvokeAll-Methode | Microsoft Docs'
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
ms.openlocfilehash: 00bce09f9e081bb0cd5c01115b05e4d3268d7293
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882614"
---
# <a name="eventsourceinvokeall-method"></a>EventSource::InvokeAll-Methode
Ruft jede zugeordnete aktuellen Ereignishandler [EventSource](../windows/eventsource-class.md) -Objekt mit den angegebenen Argumenttypen und -Argumente.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
#### <a name="parameters"></a>Parameter  
 `T0`  
 Der Typ der Ereignisarguments Handler nullte.  
  
 `T1`  
 Der Typ des ersten Arguments der Ereignis-Handler.  
  
 `T2`  
 Der Typ des zweiten Arguments der Ereignis-Handler.  
  
 `T3`  
 Der Typ des dritten Arguments der Ereignis-Handler.  
  
 `T4`  
 Der Typ der vierten Handler Ereignisarguments.  
  
 `T5`  
 Der Typ der fünften Handler Ereignisarguments.  
  
 `T6`  
 Der Typ der sechsten Handler Ereignisarguments.  
  
 `T7`  
 Der Typ der siebten Handler Ereignisarguments.  
  
 `T8`  
 Der Typ der Ereignisarguments Handler achte.  
  
 `T9`  
 Der Typ des neunten Handler Ereignisarguments.  
  
 `arg0`  
 Das Argument der nullte Ereignis-Handler.  
  
 `arg1`  
 Das erste Argument der Ereignis-Handler.  
  
 `arg2`  
 Das zweite Argument der Ereignis-Handler.  
  
 `arg3`  
 Das dritte Argument der Ereignis-Handler.  
  
 `arg4`  
 Das vierte Argument des Ereignis-Handler.  
  
 `arg5`  
 Das fünfte Argument der Ereignis-Handler.  
  
 `arg6`  
 Das sechste Ereignis-Handler-Argument.  
  
 `arg7`  
 Das siebte Ereignis-Handler-Argument.  
  
 `arg8`  
 Das achte-Ereignis-Handler-Argument.  
  
 `arg9`  
 Das neunte Ereignis-Handler-Argument.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [EventSource-Klasse](../windows/eventsource-class.md)