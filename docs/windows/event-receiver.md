---
title: Event_receiver | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.event_receiver
dev_langs:
- C++
helpviewer_keywords:
- event_receiver attribute
- event receivers
- events [C++], event receivers (sinks)
- event handling [C++], attributes
- event handling [C++], creating receiver
- event sinks, creating
- event sinks
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 01ab5aeee7d706da7016cb1ea1f01ff7367de888
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="eventreceiver"></a>event_receiver
Erstellt einen Ereignisempfänger (Senke).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ event_receiver(  
   type   
   [, layout_dependent=false]   
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 `type`  
 Eine Enumeration von einem der folgenden Werte:  
  
-   `native` für nicht verwalteten C/C++-Code (Standard für systemeigene Klassen).  
  
-   `com` für COM-Code. Dieser Wert erfordert, dass Sie folgende Headerdateien einschließen:  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **layout_dependent**  
 Geben Sie *Layout_dependent* nur, wenn `type` = **com**. *Layout_dependent* ist ein boolescher Wert:  
  
-   **"true"** bedeutet, dass die Signatur des Delegaten, den Fall, dass Empfänger genau übereinstimmen muss mit denen sie der Quelle verknüpft sind. Der Empfänger Ereignishandlernamen müssen in der Quellschnittstelle des entsprechenden Ereignisses festgelegten Namen übereinstimmen. Verwenden Sie **Coclass** Wenn *Layout_dependent* ist **"true"**. Es ist etwas effizienter an **"true"**.  
  
-   **"false"** (Standard) bedeutet, dass der aufrufende Klasse der Aufrufkonvention und die Speicherklasse (virtuell, statisch, und andere) müssen nicht die Ereignismethode und den Ereignishandler; entsprechen noch müssen die Handlernamen die Ereignisnamen Quelle Schnittstelle Methode übereinstimmen.  
  
## <a name="remarks"></a>Hinweise  
 Die **Event_receiver** C++-Attribut gibt an, dass die Klasse oder Struktur, die auf das es angewendet wird einen Ereignisempfänger mithilfe der Visual C++ einheitliche Ereignismodell wird.  
  
 **Event_receiver** wird verwendet, mit der [Event_source](../windows/event-source.md) Attribut und der [__hook](../cpp/hook.md) und [__unhook](../cpp/unhook.md) Schlüsselwörter. Verwendung **Event_source** Ereignisquellen zu erstellen. Verwendung `__hook` innerhalb des Ereignisempfängers-Methoden ("Hook") Ereignismethoden Empfänger auf die Ereignisse einer Ereignisquelle zuordnen. Verwendung `__unhook` um sie zu trennen.  
  
 *Layout_dependent* wird nur angegeben, für COM-Ereignisempfänger (`type`=**com**). Die Standardeinstellung für *Layout_dependent* ist **"false"**.  
  
> [!NOTE]
>  Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**Co-Klasse** Wenn *Layout_dependent*=**"true"**|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Compilerattribute](../windows/compiler-attributes.md)   
 [event_source](../windows/event-source.md)   
 [__event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__unhook](../cpp/unhook.md)   
 [Klassenattribute](../windows/class-attributes.md)   
