---
title: Event_source | Microsoft-Dokumentation
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
ms.openlocfilehash: e44b5757ea7b9e469275688443ba7ed1e3810571
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571388"
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
  
### <a name="parameters"></a>Parameter  
 *Typ*  
 Eine Enumeration von einem der folgenden Werte:  
  
-   `native` für nicht verwalteten C/C++-Code (Standard für nicht verwaltete Klassen).  
  
-   `com` für COM-Code. Sie müssen `coclass` verwenden, wenn `type`=`com`. Dieser Wert erfordert, dass Sie folgende Headerdateien einschließen:  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 *optimize*  
 Wenn *Typ* ist `native`, können Sie angeben, `optimize=size`, um anzugeben, dass es 4 Bytes Speicherplatz (minimum) für alle Ereignisse in einer Klasse oder `optimize=speed` (Standard), um anzugeben, dass es 4 * (Anzahl von Ereignissen)-Bytes im Speicher.  
  
 *ergänzen Sie*  
 Wenn *Typ* ist `native`, können Sie angeben, `decorate=false`, um anzugeben, dass der erweiterte Name in der zusammengeführten Datei (.mrg) nicht den Klassennamen der einschließenden enthalten soll. Mit[/Fx](../build/reference/fx-merge-injected-code.md) können Sie MRG-Dateien generieren. `decorate=false`, ist die Standardeinstellung und führt zu vollqualifizierten Typnamen in der zusammengeführten Datei.  
  
## <a name="remarks"></a>Hinweise  
 Das C++-Attribut **event_source** gibt an, dass die Klasse oder Struktur, auf die es angewendet wird, eine Ereignisquelle sein wird.  
  
 **event_source** wird in Verbindung mit dem Attribut [event_receiver](../windows/event-receiver.md) und dem Schlüsselwort [__event](../cpp/event.md) verwendet. Verwendung `event_receiver` um Ereignisempfänger zu erstellen. Verwendung **__event** für Methoden in die Ereignisquelle, die diese Methoden als Ereignisse anzugeben.  
  
> [!NOTE]
>  Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, **Struktur**|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**Co-Klasse** bei `type`=`com`|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Compilerattribute](../windows/compiler-attributes.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__unhook](../cpp/unhook.md)   
 [Klassenattribute](../windows/class-attributes.md)   