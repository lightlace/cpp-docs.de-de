---
title: Event_receiver | Microsoft-Dokumentation
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
ms.openlocfilehash: 23607eb9d59a5c860d89444205c675c95e2b907e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594068"
---
# <a name="eventreceiver"></a>event_receiver

Erstellt einen Ereignisempfänger (Senke).

## <a name="syntax"></a>Syntax

```cpp
[ event_receiver(
   type
   [, layout_dependent=false]
) ]
```

### <a name="parameters"></a>Parameter

*Typ*  
Eine Enumeration von einem der folgenden Werte:

- `native` für nicht verwalteten C/C++-Code (Standard für native Klassen).

- `com` für COM-Code. Dieser Wert erfordert, dass Sie folgende Headerdateien einschließen:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*layout_dependent*  
Geben Sie *Layout_dependent* nur, wenn `type` = **com**. *Layout_dependent* ist ein boolescher Wert:

- **"true"** bedeutet, dass die Signatur des Delegaten, den Fall, dass Empfänger genau übereinstimmen muss, sie in dieser Quelle verknüpft sind. Der Empfänger Ereignishandlernamen müssen es sich um den in der Quellschnittstelle des relevanten Ereignisses angegebenen Namen übereinstimmen. Verwenden Sie `coclass` beim *Layout_dependent* ist **"true"**. Es ist etwas effizienter an **"true"**.

- **"false"** (Standard) bedeutet, dass die aufrufende Klasse der Aufrufkonvention und die Speicherklasse (virtuell, statisch, usw.) müssen nicht die Ereignismethode und den Handlern; entsprechen, noch müssen die Handlernamen die Source-Schnittstelle Methode Ereignisnamen übereinstimmen.

## <a name="remarks"></a>Hinweise

Die **Event_receiver** C++-Attribut gibt an, dass die Klasse oder Struktur, die auf das er angewendet wird einen Ereignisempfänger, verwenden das einheitliche Ereignismodell für die Visual C++ wird.

**Event_receiver** wird zusammen mit den [Event_source](../windows/event-source.md) Attribut und die [__hook](../cpp/hook.md) und [__unhook](../cpp/unhook.md) Schlüsselwörter. Verwendung `event_source` zum Erstellen von Ereignisquellen. Verwendung **__hook** einen Ereignisempfänger Methoden ("Hook") Event Receiver-Methoden, Ereignisse aus einer Ereignisquelle zu verknüpfen. Verwendung **__unhook** um sie zu trennen.

*Layout_dependent* wird nur bei COM-Ereignisempfängern angegeben (`type`=**com**). Der Standardwert für *Layout_dependent* ist **"false"**.

> [!NOTE]
> Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|`coclass` Wenn *Layout_dependent*=**"true"**|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[Compilerattribute](../windows/compiler-attributes.md)  
[event_source](../windows/event-source.md)  
[__event](../cpp/event.md)  
[__hook](../cpp/hook.md)  
[__unhook](../cpp/unhook.md)  
[Klassenattribute](../windows/class-attributes.md)  