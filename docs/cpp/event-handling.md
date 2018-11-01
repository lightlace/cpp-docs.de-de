---
title: Ereignisbehandlung
ms.date: 11/04/2016
helpviewer_keywords:
- attributes [C++], event handling
- intrinsic functions [C++], event handling
- event handling [C++], Visual C++
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
ms.openlocfilehash: d1a89d5afce2e3715b5a61c0815d88ed2fbae8b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523245"
---
# <a name="event-handling"></a>Ereignisbehandlung

Ereignisbehandlung wird hauptsächlich für COM-Klassen unterstützt (C++-Klassen, die COM-Objekten, die in der Regel mit ATL-Klassen implementieren oder die [Co-Klasse](../windows/coclass.md) Attribut).  Weitere Informationen finden Sie unter [Ereignisbehandlung in COM](../cpp/event-handling-in-com.md).

Ereignisbehandlung wird auch für native C++-Klassen (C++-Klassen, die keine COM-Objekte implementieren) unterstützt. Die Unterstützung ist jedoch veraltet und wird in einem der nächsten Releases entfernt werden.  Weitere Informationen finden Sie unter [Ereignisbehandlung in systemeigenem C++](../cpp/event-handling-in-native-cpp.md).

Die Ereignisbehandlung unterstützt Einzel- und Multithreadverwendung und schützt Daten vor gleichzeitigem Multithreadzugriff. Sie ermöglicht Ihnen auch das Ableiten von Unterklassen aus Ereignisquellklassen oder Ereignisempfängerklassen und unterstützt die erweiterte Ereignisquellentnahme bzw. den Ereignisempfang in der abgeleiteten Klasse.

Visual C++ enthält Attribute und Schlüsselwörter zum Deklarieren von Ereignissen und Ereignishandlern. Die Ereignisattribute und Schlüsselwörter können in CLR-Programmen und in systemeigenen C++-Programmen verwendet werden.

|Thema|Beschreibung|
|-----------|-----------------|
|[event_source](../windows/event-source.md)|Erstellt eine Ereignisquelle.|
|[event_receiver](../windows/event-receiver.md)|Erstellt einen Ereignisempfänger (Senke).|
|[__event](../cpp/event.md)|Deklariert ein Ereignis.|
|[__raise](../cpp/raise.md)|Hebt die Aufrufsite eines Ereignisses hervor.|
|[__hook](../cpp/hook.md)|Ordnet eine Handlermethode einem Ereignis zu.|
|[__unhook](../cpp/unhook.md)|Trennt eine Handlermethode von einem Ereignis.|

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)