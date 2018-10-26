---
title: Compilerattribute (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: 95e5d65d437b60f6421978682997067d8f53a3d5
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50073954"
---
# <a name="eventreceiver"></a>event_receiver

Erstellt einen Ereignisempfänger (Senke).

## <a name="syntax"></a>Syntax

```cpp
[ event_receiver(type
   [, layout_dependent=false]) ]
```

### <a name="parameters"></a>Parameter

*Typ*<br/>
Eine Enumeration von einem der folgenden Werte:

- `native` für nicht verwalteten C/C++-Code (Standard für native Klassen).

- `com` für COM-Code. Dieser Wert erfordert, dass Sie folgende Headerdateien einschließen:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*layout_dependent*<br/>
Geben Sie *Layout_dependent* nur, wenn `type` = **com**. *Layout_dependent* ist ein boolescher Wert:

- **"true"** bedeutet, dass die Signatur des Delegaten, den Fall, dass Empfänger genau übereinstimmen muss, sie in dieser Quelle verknüpft sind. Der Empfänger Ereignishandlernamen müssen es sich um den in der Quellschnittstelle des relevanten Ereignisses angegebenen Namen übereinstimmen. Verwenden Sie `coclass` beim *Layout_dependent* ist **"true"**. Es ist etwas effizienter an **"true"**.

- **"false"** (Standard) bedeutet, dass die aufrufende Klasse der Aufrufkonvention und die Speicherklasse (virtuell, statisch, usw.) müssen nicht die Ereignismethode und den Handlern; entsprechen, noch müssen die Handlernamen die Source-Schnittstelle Methode Ereignisnamen übereinstimmen.

## <a name="remarks"></a>Hinweise

Die **Event_receiver** C++-Attribut gibt an, dass die Klasse oder Struktur, die auf das er angewendet wird einen Ereignisempfänger, verwenden das einheitliche Ereignismodell für die Visual C++ wird.

**Event_receiver** wird zusammen mit den [Event_source](event-source.md) Attribut und die [__hook](../../cpp/hook.md) und [__unhook](../../cpp/unhook.md) Schlüsselwörter. Verwendung `event_source` zum Erstellen von Ereignisquellen. Verwendung **__hook** einen Ereignisempfänger Methoden ("Hook") Event Receiver-Methoden, Ereignisse aus einer Ereignisquelle zu verknüpfen. Verwendung **__unhook** um sie zu trennen.

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

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[Compilerattribute](compiler-attributes.md)<br/>
[event_source](event-source.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[Klassenattribute](class-attributes.md)