---
title: "Funktionsobjekte in der STL"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Funktionselemente"
  - "C++-Standardbibliothek, Funktionselemente"
  - "C++-Standardbibliothek, Funktionsobjekte"
  - "function-Objekte"
ms.assetid: 85f8a735-2c7b-4f10-9c4d-95c666ec4192
caps.latest.revision: 6
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Funktionsobjekte in der STL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein *Funktionsobjekt* oder *Funktionselement* ist ein beliebiger Typ, der „operator\(\)“ implementiert. Dieser Operator wird als *Aufrufoperator* oder manchmal als *Anwendungsoperator* bezeichnet. Die Standard Template Library verwendet Funktionsobjekte hauptsächlich als Sortierungskriterien für Container und in den Algorithmen.  
  
 „Funktionsobjekte“ bieten gegenüber einem konventionellen Funktionsaufruf zwei wesentliche Vorteile. Der erste Vorteil ist, dass ein Funktionsobjekt einen Zustand enthalten kann. Der zweite Vorteil ist, dass ein Funktionsobjekt ein Typ ist und daher nicht als Vorlagenparameter verwendet werden kann.  
  
## Erstellen eines Funktionsobjekts  
 Um ein Funktionsobjekt zu erstellen, erstellen Sie einen Typ, und implementieren Sie „operator\(\)“, z. B.:  
  
```  
class Functor { public: int operator()(int a, int b) { return a < b; } }; int main() { Functor f; int a = 5; int b = 7; int ans = f(a, b); }  
```  
  
 Die letzte Zeile der `main`\-Funktion zeigt, wie Sie das Funktionsobjekt aufrufen. Dieser Aufruf ähnelt einem Aufruf einer Funktion. Tatsächlich wird aber „operator\(\)“ des Typs „Funktionselement“ aufgerufen. Diese Ähnlichkeit zwischen dem Aufruf eines Funktionsobjekts und einer Funktion hat zum Begriff „Funktionsobjekt“ geführt.  
  
## Funktionsobjekte und Container  
 Die Standard Template Library enthält mehrere Funktionsobjekte in der [\<functional\>](../standard-library/functional.md)\-Headerdatei. Eine Verwendung dieser Funktionsobjekte ist als Sortierungskriterium für Container. Beispielsweise wird der `set`\-Container wie folgt deklariert:  
  
```  
template < class Key, class Traits=less<Key>, class Allocator=allocator<Key> > class set  
```  
  
 Das zweite Vorlagenargument ist das Funktionsobjekt „`less`“. Dieses Funktionsobjekt gibt `true` zurück, wenn der erste an sie übergebene Parameter kleiner als der zweite übergebene Parameter ist. Da einige Container ihre Elemente sortieren, benötigt der Container eine Möglichkeit zum Vergleich von zwei Elementen, und dies wird mithilfe des Funktionsobjekts erreicht. Sie können eigene Sortierungskriterien für Container definieren, indem Sie ein Funktionsobjekt erstellen und es in der Vorlagenliste für den Container angeben.  
  
## Funktionsobjekte und Algorithmen  
 Eine weitere Verwendungsmöglichkeit von Funktionsobjekten ist in Algorithmen. Beispielsweise wird der `remove_if`\-Algorithmus wie folgt deklariert:  
  
```  
template<class ForwardIterator, class Predicate> ForwardIterator remove_if( ForwardIterator _First, ForwardIterator _Last, Predicate _Pred );  
```  
  
 Das letzte Argument für `remove_if` ist ein Funktionsobjekt, das einen booleschen Wert zurückgibt \(ein *Prädikat*\). Wenn das Ergebnis des Funktionsobjekts `true` ist, wird das Element aus dem Container entfernt, auf den die Iteratoren `_First` und `_Last` zugreifen. Sie können eines der Funktionsobjekte verwenden, die im [\<functional\>](../standard-library/functional.md)\-Header für das Argument `_Pred` deklariert sind, oder ein eigenes erstellen.  
  
## Siehe auch  
 [Standard Template Library](../misc/standard-template-library.md)