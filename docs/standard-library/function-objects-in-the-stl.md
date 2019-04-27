---
title: Funktionsobjekte in der C++-Standardbibliothek
ms.date: 03/15/2019
helpviewer_keywords:
- functors
- C++ Standard Library, functors
- C++ Standard Library, function objects
- function objects
ms.assetid: 85f8a735-2c7b-4f10-9c4d-95c666ec4192
ms.openlocfilehash: 310d846285612ad94ec9d66672fcb996557b07e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159365"
---
# <a name="function-objects-in-the-c-standard-library"></a>Funktionsobjekte in der C++-Standardbibliothek

Ein *Funktionsobjekt*oder *Funktionselement*ist ein beliebiger Typ, der „operator()“ implementiert. Dieser Operator wird als *Aufrufoperator* oder manchmal als *Anwendungsoperator*bezeichnet. Die C++-Standardbibliothek verwendet Funktionsobjekte hauptsächlich als Sortierungskriterien für Container und in Algorithmen.

„Funktionsobjekte“ bieten gegenüber einem konventionellen Funktionsaufruf zwei wesentliche Vorteile. Der erste Vorteil ist, dass ein Funktionsobjekt einen Zustand enthalten kann. Der zweite Vorteil ist, dass ein Funktionsobjekt ein Typ ist und daher nicht als Vorlagenparameter verwendet werden kann.

## <a name="creating-a-function-object"></a>Erstellen eines Funktionsobjekts

Um ein Funktionsobjekt zu erstellen, erstellen Sie einen Typ, und implementieren Sie „operator()“, z. B.:

```cpp
class Functor
{
public:
    int operator()(int a, int b)
    {
        return a < b;
    }
};

int main()
{
    Functor f;
    int a = 5;
    int b = 7;
    int ans = f(a, b);
}
```

Die letzte Zeile der `main` -Funktion zeigt, wie Sie das Funktionsobjekt aufrufen. Dieser Aufruf ähnelt einem Aufruf einer Funktion, aber es tatsächlich aufrufende operator() des Typs "Funktionselement" aus. Diese Ähnlichkeit zwischen dem Aufruf eines Funktionsobjekts und einer Funktion hat zum Begriff „Funktionsobjekt“ geführt.

## <a name="function-objects-and-containers"></a>Funktionsobjekte und Container

Die C++-Standardbibliothek enthält mehrere Funktionsobjekte in der Headerdatei [\<functional>](../standard-library/functional.md). Eine Verwendung dieser Funktionsobjekte ist als Sortierungskriterium für Container. Beispielsweise wird der `set` -Container wie folgt deklariert:

```cpp
template <class Key,
    class Traits=less<Key>,
    class Allocator=allocator<Key>>
class set
```

Das zweite Vorlagenargument ist das Funktionsobjekt „ `less`“. Dieses Funktionsobjekt gibt **"true"** , wenn der erste Parameter kleiner ist als der zweite Parameter. Da einige Container ihre Elemente sortieren, benötigt der Container eine Möglichkeit zum Vergleichen von zwei Elementen. Der Vergleich erfolgt mithilfe der Function-Objekt. Sie können eigene Sortierungskriterien für Container definieren, indem Sie ein Funktionsobjekt erstellen und es in der Vorlagenliste für den Container angeben.

## <a name="function-objects-and-algorithms"></a>Funktionsobjekte und Algorithmen

Eine weitere Verwendungsmöglichkeit von Funktionsobjekten ist in Algorithmen. Beispielsweise wird der `remove_if` -Algorithmus wie folgt deklariert:

```cpp
template <class ForwardIterator, class Predicate>
ForwardIterator remove_if(
    ForwardIterator first,
    ForwardIterator last,
    Predicate pred);
```

Das letzte Argument für `remove_if` ist ein Funktionsobjekt, das einen booleschen Wert zurückgibt (ein *Prädikat*). Wenn das Ergebnis des Funktionsobjekts **"true"**, und klicken Sie dann das Element entfernt wird, aus dem Container, die Zugriff auf die Iteratoren `first` und `last`. Sie können eines der Funktionsobjekte verwenden, die im Header [\<functional>](../standard-library/functional.md) für das Argument `pred` deklariert sind, oder ein eigenes erstellen.

## <a name="see-also"></a>Siehe auch

[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
