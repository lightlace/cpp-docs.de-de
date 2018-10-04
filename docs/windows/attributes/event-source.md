---
title: Event_source (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: 750e51264f12d1c8961ced4e8b606ea5d040d8c9
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791299"
---
# <a name="eventsource"></a>event_source

Erstellt eine Ereignisquelle.

## <a name="syntax"></a>Syntax

```cpp
[ event_source(type, optimize=[speed | size], decorate=[true | false]) ]
```

### <a name="parameters"></a>Parameter

*Typ*<br/>
Eine Enumeration von einem der folgenden Werte:

- `native` für nicht verwalteten C/C++-Code (Standard für nicht verwaltete Klassen).

- `com` für COM-Code. Sie müssen `coclass` verwenden, wenn `type`=`com`. Dieser Wert erfordert, dass Sie folgende Headerdateien einschließen:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*optimize*<br/>
Wenn *Typ* ist `native`, können Sie angeben, `optimize=size`, um anzugeben, dass es 4 Bytes Speicherplatz (minimum) für alle Ereignisse in einer Klasse oder `optimize=speed` (Standard), um anzugeben, dass es 4 * (Anzahl von Ereignissen)-Bytes im Speicher.

*ergänzen Sie*<br/>
Wenn *Typ* ist `native`, können Sie angeben, `decorate=false`, um anzugeben, dass der erweiterte Name in der zusammengeführten Datei (.mrg) nicht den Klassennamen der einschließenden enthalten soll. [/ FX](../../build/reference/fx-merge-injected-code.md) können Sie MRG-Dateien zu generieren. `decorate=false`, ist die Standardeinstellung und führt zu vollqualifizierten Typnamen in der zusammengeführten Datei.

## <a name="remarks"></a>Hinweise

Das C++-Attribut **event_source** gibt an, dass die Klasse oder Struktur, auf die es angewendet wird, eine Ereignisquelle sein wird.

**Event_source** dient in Verbindung mit der [Event_receiver](event-receiver.md) Attribut und die [__event](../../cpp/event.md) Schlüsselwort. Verwendung `event_receiver` um Ereignisempfänger zu erstellen. Verwendung **__event** für Methoden in die Ereignisquelle, die diese Methoden als Ereignisse anzugeben.

> [!NOTE]
> Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|**Co-Klasse** bei `type`=`com`|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[Compilerattribute](compiler-attributes.md)<br/>
[event_receiver](event-receiver.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[Klassenattribute](class-attributes.md)  