---
title: __hook
ms.date: 11/04/2016
f1_keywords:
- __hook_cpp
helpviewer_keywords:
- __hook keyword [C++]
- event handlers [C++], connecting events to
ms.assetid: f4cabb10-d293-4c0e-a1d2-4745ef9cc22c
ms.openlocfilehash: c4887d85e01344c171fb0fdfe957f2d8a669ff6a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58771668"
---
# <a name="hook"></a>__hook

Ordnet eine Handlermethode einem Ereignis zu.

## <a name="syntax"></a>Syntax

```
long __hook(
    &SourceClass::EventMethod,
    source,
    &ReceiverClass::HandlerMethod
    [, receiver = this]
);
long __hook(
    interface,
    source
);
```

### <a name="parameters"></a>Parameter

*& SourceClass::EventMethod*<br/>
Ein Zeiger auf die Ereignismethode, an die Sie die Ereignishandlermethode binden:

- Systemeigene C++-Ereignisse: *SourceClass* ist die Ereignisquellenklasse, und *EventMethod* ist das Ereignis.

- COM-Ereignisse: *SourceClass* ist die Quellschnittstelle des Ereignisses und *EventMethod* ist einer der Methoden.

- Verwaltete Ereignisse: *SourceClass* ist die Ereignisquellenklasse, und *EventMethod* ist das Ereignis.

*interface*<br/>
Der Name der Schnittstelle verknüpft wird, um *Empfänger*, nur für COM-Ereignisempfängern, bei denen die *Layout_dependent* Parameter der [Event_receiver](../windows/attributes/event-receiver.md) -Attribut ist **"true"**.

*source*<br/>
Ein Zeiger auf eine Instanz der Ereignisquelle. Je nach Code `type` im angegebenen `event_receiver`, *Quelle* kann einen der folgenden sein:

- Ein systemeigener Ereignisquellen-Objektzeiger.

- Ein `IUnknown`-basierte Zeiger (COM-Quelle).

- Ein Zeiger des verwalteten Objekts (für verwaltete Ereignisse).

*& ReceiverClass::HandlerMethod*<br/>
Ein Zeiger, der an die Ereignishandlermethode gebunden werden soll. Der Handler, die als eine Methode einer Klasse oder einen Verweis auf die gleiche angegeben ist. Wenn Sie nicht den Klassennamen angeben **__hook** geht davon aus der Klasse, in dem sie aufgerufen wird.

- Systemeigene C++-Ereignisse: *ReceiverClass* ist die Ereignisempfängerklasse und `HandlerMethod` ist der Handler.

- COM-Ereignisse: *ReceiverClass* ist die ereignisempfängerschnittstelle und `HandlerMethod` ist einer der Handler.

- Verwaltete Ereignisse: *ReceiverClass* ist die Ereignisempfängerklasse und `HandlerMethod` ist der Handler.

*receiver*<br/>
(Optional) Ein Zeiger auf eine Instanz von der Ereignisempfängerklasse. Wenn Sie keinen Empfänger angeben, wird standardmäßig die Empfängerklasse oder Struktur, in der **__hook** aufgerufen wird.

## <a name="usage"></a>Verwendung

Kann in jedem Gültigkeitsbereich der Funktion verwendet werden, einschließlich Main, außerhalb der Ereignisempfängerklasse.

## <a name="remarks"></a>Hinweise

Die intrinsische Funktion **__hook** in einem Ereignisempfänger zuweisen oder eine Handlermethode einer Ereignismethode zu verknüpfen. Der angegebene Handler wird aufgerufen, wenn die Quelle das angegebene Ereignis auslöst. Sie können mehrere Handler an ein einzelnes Ereignis binden oder mehrere Ereignisse an einen einzigen Handler.

Es gibt zwei Arten von **__hook**. Können Sie die erste Form (vier Argumente) in den meisten Fällen, insbesondere für COM-Ereignisempfängern, bei denen die *Layout_dependent* Parameter, der die [Event_receiver](../windows/attributes/event-receiver.md) -Attribut ist **"false"** .

In diesen Fällen müssen Sie nicht alle Methoden an eine Schnittstelle binden, bevor nicht bei einer der Methoden ein Ereignis ausgelöst wird; nur die Methode für die Ereignisbehandlung muss eingebunden werden. Sie können das zweite (Two-Argument) Formular von **__hook** nur für einen COM-Ereignisempfänger, in dem *Layout_dependent* **= True**.

**__hook** gibt einen long-Wert. Ein Wert ungleich null gibt an, dass ein Fehler aufgetreten ist (verwaltete Ereignisse lösen eine Ausnahme aus).

Der Compiler überprüft, ob ein Ereignis vorhanden ist und ob die Ereignissignatur der Delegatsignatur entspricht.

Mit Ausnahme von COM-Ereignisse **__hook** und **__unhook** außerhalb des Ereignisempfängers aufgerufen werden kann.

Eine Alternative zur Verwendung **__hook** ist die Verwendung des Operators +=.

Weitere Informationen über die Codierung von verwalteter Ereignissen in der neuen Syntax finden Sie unter [Ereignis](../extensions/event-cpp-component-extensions.md).

> [!NOTE]
> Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.

## <a name="example"></a>Beispiel

Finden Sie unter [Ereignisbehandlung in systemeigenem C++](../cpp/event-handling-in-native-cpp.md) und [Ereignisbehandlung in COM](../cpp/event-handling-in-com.md) für Beispiele.

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[Ereignisbehandlung](../cpp/event-handling.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__unhook](../cpp/unhook.md)<br/>
[__raise](../cpp/raise.md)<br/>
