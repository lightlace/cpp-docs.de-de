---
title: "EventSource::InvokeAll-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource::InvokeAll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InvokeAll-Methode"
ms.assetid: 1506618f-0421-4428-a4d0-4ea2b10a3bf6
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# EventSource::InvokeAll-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft jede Ereignishandler mit dem aktuellen [EventSource](../windows/eventsource-class.md) -Objekt mit den angegebenen Argumenttypen und -Argumente.  
  
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
 Der Typ der nullten Ereignis-Handler-Argument.  
  
 `T1`  
 Der Typ des ersten Arguments der Ereignis-Handler.  
  
 `T2`  
 Der Typ des zweiten Arguments der Ereignis-Handler.  
  
 `T3`  
 Der Typ des dritten Arguments der Ereignis-Handler.  
  
 `T4`  
 Der Typ des vierten Ereignis-Handler-Argument.  
  
 `T5`  
 Der Typ des fünften Ereignis-Handler-Argument.  
  
 `T6`  
 Der Typ des sechsten Ereignis-Handler-Argument.  
  
 `T7`  
 Der Typ des siebten Ereignis-Handler-Argument.  
  
 `T8`  
 Der Typ des achte Ereignis-Handler-Argument.  
  
 `T9`  
 Der Typ des neunten Ereignis-Handler-Argument.  
  
 `arg0`  
 Die nullte-Ereignis-Handler-Argument.  
  
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
 Der achte-Ereignis-Handler-Argument.  
  
 `arg9`  
 Das neunte Ereignis-Handler-Argument.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [EventSource-Klasse](../windows/eventsource-class.md)