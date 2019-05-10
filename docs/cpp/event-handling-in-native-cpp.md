---
title: Ereignisbehandlung in systemeigenem C++
ms.date: 05/07/2019
helpviewer_keywords:
- event handling [C++]
ms.assetid: e4b9219a-15d8-42fb-83c8-6d2e4e087c8d
ms.openlocfilehash: 9eb0334e3633921842fcc06155ba0300ff6192e1
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222187"
---
# <a name="event-handling-in-native-c"></a>Ereignisbehandlung in systemeigenem C++

In systemeigenen C++ Ereignisbehandlung müssen Sie eine Ereignisquelle und einen Ereignisempfänger mithilfe der [Event_source](../windows/attributes/event-source.md) und [Event_receiver](../windows/attributes/event-receiver.md) -Attribute angeben `type` =`native`. Diese Attribute ermöglichen es den Klassen, auf die sie angewendet werden, in einem systemeigenen Nicht-COM-Kontext Ereignisse auszulösen und Ereignisse zu behandeln.

## <a name="declaring-events"></a>Deklarieren von Ereignissen

In einer ereignisquellklasse verwenden die [__event](../cpp/event.md) Schlüsselwort in einer Methodendeklaration, um die Methode als ein Ereignis zu deklarieren. Stellen Sie sicher, dass Sie die Methode deklarieren, aber nicht definieren. Andernfalls wird ein Compilerfehler verursacht, da der Compiler die Methode implizit definiert, wenn er in einem Ereignis ausgeführt wird. Systemeigene Ereignisse können Methoden mit null oder mehr Parametern sein. Der Rückgabetyp kann „void“ oder ein ganzzahliger Typ sein.

## <a name="defining-event-handlers"></a>Definieren von Ereignishandlern

In einer Ereignisempfängerklasse definieren Sie Ereignishandler, die Methoden mit Signaturen sind (Rückgabetypen, Argumente und Aufrufkonventionen), die mit dem Ereignis übereinstimmen, das sie behandeln.

## <a name="hooking-event-handlers-to-events"></a>Verknüpfen von Ereignishandlern mit Ereignissen

In einer Ereignisempfängerklasse, verwenden Sie auch die intrinsische Funktion [__hook](../cpp/hook.md) um Ereignisse Ereignishandlern zuzuordnen und [__unhook](../cpp/unhook.md) um Ereignisse von Ereignishandlern zu trennen. Sie können mehrere Ereignisse mit einem Ereignishandler oder mehrere Ereignishandler mit einem Ereignis verknüpfen.

## <a name="firing-events"></a>Auslösen von Ereignissen

Um ein Ereignis auszulösen, rufen Sie einfach die Methode auf, die als Ereignis in der Ereignisquellen-Klasse deklariert wurde. Wenn Handler an das Ereignis geknüpft wurden, werden die Handler aufgerufen.

### <a name="native-c-event-code"></a>Systemeigener C++-Ereigniscode

Das folgende Beispiel zeigt, wie ein Ereignis im systemeigenen C++-Code ausgelöst wird. Informationen zum Kompilieren und Ausführen des Beispiels finden Sie in den Kommentaren im Code.

## <a name="example"></a>Beispiel

### <a name="code"></a>Code

```cpp
// evh_native.cpp
#include <stdio.h>

[event_source(native)]
class CSource {
public:
   __event void MyEvent(int nValue);
};

[event_receiver(native)]
class CReceiver {
public:
   void MyHandler1(int nValue) {
      printf_s("MyHandler1 was called with value %d.\n", nValue);
   }

   void MyHandler2(int nValue) {
      printf_s("MyHandler2 was called with value %d.\n", nValue);
   }

   void hookEvent(CSource* pSource) {
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);
   }

   void unhookEvent(CSource* pSource) {
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);
   }
};

int main() {
   CSource source;
   CReceiver receiver;

   receiver.hookEvent(&source);
   __raise source.MyEvent(123);
   receiver.unhookEvent(&source);
}
```

### <a name="output"></a>Output

```Output
MyHandler2 was called with value 123.
MyHandler1 was called with value 123.
```

## <a name="see-also"></a>Siehe auch

[Ereignisbehandlung](../cpp/event-handling.md)