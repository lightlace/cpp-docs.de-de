---
title: Event_source | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.event_source
dev_langs:
- C++
helpviewer_keywords:
- event handling, attributes
- event logs, event source
- event sources, creating
- event_source attribute
- event sources
- event handling, creating event source
ms.assetid: 0983e36a-6127-4fbb-8a22-8dfec6564c16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b7e7e287d68bac0fe69417fe21df27ed3231cce6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879382"
---
# <a name="eventsource"></a>event_source
Erstellt eine Ereignisquelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ event_source(  
   type,  
   optimize=[speed | size],  
   decorate=[true | false]  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 `type`  
 Eine Enumeration von einem der folgenden Werte:  
  
-   `native` für nicht verwalteten C/C++-Code (Standard für nicht verwaltete Klassen).  
  
-   `com` für COM-Code. Sie müssen `coclass` verwenden, wenn `type`=`com`. Dieser Wert erfordert, dass Sie folgende Headerdateien einschließen:  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **optimize**  
 Wenn `type` **native**ist, können Sie **optimize=size**angeben, um anzugeben, dass mindestens 4 Bytes Speicherplatz für alle Ereignisse in einer Klasse vorhanden sind, oder **optimize=speed** (Standard), um anzuzeigen, dass für jedes Event 4 * Bytes Speicherplatz zur Verfügung stehen.  
  
 **decorate**  
 Wenn `type` **native**ist, können Sie **decorate=false**angeben, um anzugeben, dass der erweiterte Name in der zusammengeführten Datei (.mrg) nicht den Namen der einschließenden Klasse enthalten soll. Mit[/Fx](../build/reference/fx-merge-injected-code.md) können Sie MRG-Dateien generieren. **decorate=false**, ist die Standardeinstellung und führt zu vollqualifizierten Typnamen in der zusammengeführten Datei.  
  
## <a name="remarks"></a>Hinweise  
 Das C++-Attribut **event_source** gibt an, dass die Klasse oder Struktur, auf die es angewendet wird, eine Ereignisquelle sein wird.  
  
 **event_source** wird in Verbindung mit dem Attribut [event_receiver](../windows/event-receiver.md) und dem Schlüsselwort [__event](../cpp/event.md) verwendet. Verwenden Sie **event_receiver** , um Ereignisempfänger zu erstellen. Verwenden Sie `__event` für Methoden in der Ereignisquelle, um diese Methoden als Ereignisse anzugeben.  
  
> [!NOTE]
>  Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**coclass** verwenden, wenn `type`=**com**|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Compilerattribute](../windows/compiler-attributes.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__unhook](../cpp/unhook.md)   
 [Klassenattribute](../windows/class-attributes.md)   
