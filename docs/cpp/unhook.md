---
title: __unhook
ms.date: 11/04/2016
f1_keywords:
- __unhook
- __unhook_cpp
helpviewer_keywords:
- event handlers [C++], dissociating events
- __unhook keyword [C++]
ms.assetid: 953a14f3-5199-459d-81e5-fcf015a19878
ms.openlocfilehash: f6e5031cb77729ede053b275c90fa93bf251fcb6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486774"
---
# <a name="unhook"></a>__unhook

Trennt eine Handlermethode von einem Ereignis.

## <a name="syntax"></a>Syntax

```cpp
long  __unhook(
   &SourceClass::EventMethod,
   source,
   &ReceiverClass::HandlerMethod
   [, receiver = this]
);
long  __unhook(
   interface,
   source
);
long  __unhook(
   source
);
```

#### <a name="parameters"></a>Parameter

**&** *SourceClass* `::` *EventMethod* ein Zeiger auf die Ereignismethode, von dem Sie die Ereignishandlermethode lösen:

- Systemeigene C++-Ereignisse: *SourceClass* ist die Ereignisquellenklasse, und *EventMethod* ist das Ereignis.

- COM-Ereignisse: *SourceClass* ist die Quellschnittstelle des Ereignisses und *EventMethod* ist einer der Methoden.

- Verwaltete Ereignisse: *SourceClass* ist die Ereignisquellenklasse, und *EventMethod* ist das Ereignis.

*interface*<br/>
Der Name der Schnittstelle von verknüpft wird *Empfänger*, nur für COM-Ereignisempfängern, bei denen die *Layout_dependent* Parameter der [Event_receiver](../windows/event-receiver.md) -Attribut ist **"true"**.

*source*<br/>
Ein Zeiger auf eine Instanz der Ereignisquelle. Je nach Code `type` im angegebenen `event_receiver`, *Quelle* kann einen der folgenden sein:

- Ein systemeigener Ereignisquellen-Objektzeiger.

- Ein `IUnknown`-basierte Zeiger (COM-Quelle).

- Ein Zeiger des verwalteten Objekts (für verwaltete Ereignisse).

**&** *ReceiverClass* `::` `HandlerMethod` ein Zeiger auf die Ereignishandlermethode, die von einem Ereignis entfernt, entfernt werden. Der Handler, die als eine Methode einer Klasse oder einen Verweis auf die gleiche angegeben ist. Wenn Sie nicht den Klassennamen angeben **__unhook** geht davon aus der Klasse, in dem sie aufgerufen wird.

- Systemeigene C++-Ereignisse: *ReceiverClass* ist die Ereignisempfängerklasse und `HandlerMethod` ist der Handler.

- COM-Ereignisse: *ReceiverClass* ist die ereignisempfängerschnittstelle und `HandlerMethod` ist einer der Handler.

- Verwaltete Ereignisse: *ReceiverClass* ist die Ereignisempfängerklasse und `HandlerMethod` ist der Handler.

*Empfänger*(optional) ein Zeiger auf eine Instanz von der Ereignisempfängerklasse. Wenn Sie keinen Empfänger angeben, wird standardmäßig die Empfängerklasse oder Struktur, in der **__unhook** aufgerufen wird.

## <a name="usage"></a>Verwendung

Kann in jedem Gültigkeitsbereich der Funktion verwendet werden, einschließlich Main, außerhalb der Ereignisempfängerklasse.

## <a name="remarks"></a>Hinweise

Die intrinsische Funktion **__unhook** in einem Ereignisempfänger, um die Zuordnung aufheben, oder "lösen" eine Handlermethode von einer Ereignismethode.

Es gibt drei Arten von **__unhook**. Sie können in den meisten Fällen das erste (four-argument) Formular verwenden. Sie können das zweite (Two-Argument) Formular von **__unhook** nur für einen COM-Ereignisempfänger verwenden; hebt dies die gesamte-Schnittstelle. Sie können das dritte (one-argument) Formular verwenden, um bei allen Delegaten aus der angegebenen Quelle die Bindung zu lösen.

Ein Wert ungleich null gibt an, dass ein Fehler aufgetreten ist (verwaltete Ereignisse lösen eine Ausnahme aus).

Wenn Sie aufrufen **__unhook** für ein Ereignis und Ereignishandler, der nicht bereits verknüpft sind, hat er keine Auswirkungen.

Zur Kompilierzeit überprüft der Compiler, dass das Ereignis vorhanden ist und führt eine Parametertypüberprüfung mit dem angegebenen Handler aus.

Mit Ausnahme von COM-Ereignisse **__hook** und **__unhook** außerhalb des Ereignisempfängers aufgerufen werden kann.

Eine Alternative zur Verwendung **__unhook** den =-Operator verwendet wird.

Weitere Informationen über die Codierung von verwalteter Ereignissen in der neuen Syntax finden Sie unter [Ereignis](../windows/event-cpp-component-extensions.md).

> [!NOTE]
>  Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.

## <a name="example"></a>Beispiel

Finden Sie unter [Ereignisbehandlung in systemeigenem C++](../cpp/event-handling-in-native-cpp.md) und [Ereignisbehandlung in COM](../cpp/event-handling-in-com.md) für Beispiele.

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[event_source](../windows/event-source.md)<br/>
[event_receiver](../windows/event-receiver.md)<br/>
[__event](../cpp/event.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__raise](../cpp/raise.md)