---
title: Ereignisbehandlung
ms.date: 05/07/2019
helpviewer_keywords:
- event handling [C++]
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
ms.openlocfilehash: bd74ba0b20e2058f0b04d0d0d3c22c9d526157a0
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222121"
---
# <a name="event-handling"></a>Ereignisbehandlung

Ereignisbehandlung wird hauptsächlich für COM-Klassen unterstützt (C++-Klassen, die COM-Objekten, die in der Regel mit ATL-Klassen implementieren oder die [Co-Klasse](../windows/coclass.md) Attribut). Weitere Informationen finden Sie unter [Ereignisbehandlung in COM](../cpp/event-handling-in-com.md).

Ereignisbehandlung wird auch für systemeigene C++-Klassen (C++-Klassen, die keine COM-Objekte implementieren) unterstützt. Die Unterstützung ist jedoch veraltet und wird in einer der nächsten Versionen entfernt werden.  Weitere Informationen finden Sie unter [Ereignisbehandlung in systemeigenem C++](../cpp/event-handling-in-native-cpp.md).

Die Ereignisbehandlung unterstützt Einzel- und Multithreadverwendung und schützt Daten vor gleichzeitigem Multithreadzugriff. Sie ermöglicht Ihnen auch das Ableiten von Unterklassen aus Ereignisquellklassen oder Ereignisempfängerklassen und unterstützt die erweiterte Ereignisquellentnahme bzw. den Ereignisempfang in der abgeleiteten Klasse.

Microsoft C++ Compiler umfasst, Attribute und Schlüsselwörter zum Deklarieren von Ereignissen und Ereignishandlern. Die Ereignisattribute und Schlüsselwörter können in CLR-Programmen und in systemeigenen C++-Programmen verwendet werden.

|Thema|Beschreibung|
|-----------|-----------------|
|[event_source](../windows/attributes/event-source.md)|Erstellt eine Ereignisquelle.|
|[event_receiver](../windows/attributes/event-receiver.md)|Erstellt einen Ereignisempfänger (Senke).|
|[__event](../cpp/event.md)|Deklariert ein Ereignis.|
|[__raise](../cpp/raise.md)|Hebt die Aufrufsite eines Ereignisses hervor.|
|[__hook](../cpp/hook.md)|Ordnet eine Handlermethode einem Ereignis zu.|
|[__unhook](../cpp/unhook.md)|Trennt eine Handlermethode von einem Ereignis.|

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)