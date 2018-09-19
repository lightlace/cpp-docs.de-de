---
title: Wie Catch-Blöcken ausgewertet (C++) werden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- try-catch keyword [C++], catchable types
- catch keyword [C++], types of catch handlers
- C++ exception handling, catch handlers
- exception handling, catching and deleting exceptions
- types [C++], exception handling
ms.assetid: 202dbf07-8ace-4b3b-b3ae-4b45c275e0b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe86770692554551b88e1aef9bbddc509e21f0f0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039438"
---
# <a name="how-catch-blocks-are-evaluated-c"></a>Auswerten von Catch-Blöcken (C++)

C++ ermöglicht Ihnen das Auslösen von Ausnahmen eines beliebigen Typs, obwohl im Allgemeinen empfohlen wird, Typen auszulösen, die von der std::exception abgeleitet sind. C++-Ausnahmen abgefangen werden kann, indem eine **catch** Handler, der den gleichen Typ gibt an, wie die ausgelöste Ausnahme oder ein Handler, der jeden Typ von Ausnahme abfangen kann.

Wenn der Typ der ausgelösten Ausnahme eine Klasse ist, die auch eine Basisklasse (oder Klassen) besitzt, kann sie durch Handler abgefangen werden, die Basisklassen des Ausnahmetyps oder Verweise auf Basen des Ausnahmetyps akzeptieren. Beachten Sie, dass wenn eine Ausnahme durch einen Verweis abgefangen wird, sie an das tatsächlich ausgelöste Ausnahmeobjekt gebunden ist; andernfalls ist es eine Kopie (nahezu identisch mit einem Argument für eine Funktion).

Wenn eine Ausnahme ausgelöst wird, kann es durch die folgenden Typen von abgefangen werden **catch** Handler:

- Ein Handler, der jeden Typ akzeptieren kann (mit der Auslassungszeichensyntax).

- Ein Handler, der den gleichen Typ wie das Ausnahmeobjekt akzeptiert; Da es sich um eine Kopie ist **const** und **flüchtige** Modifizierer ignoriert.

- Ein Handler, der einen Verweis auf den gleichen Typ wie das Ausnahmeobjekt akzeptiert.

- Ein Handler, der einen Verweis auf akzeptiert eine **const** oder **flüchtige** Form des gleichen Typs wie das Ausnahmeobjekt.

- Ein Handler, der eine Basisklasse des gleichen Typs wie das Ausnahmeobjekt akzeptiert. Da es sich um eine Kopie ist **const** und **flüchtige** Modifizierer ignoriert. Die **catch** Handler für eine Basisklasse muss nicht vorausgeht. der **catch** Handler für die abgeleitete Klasse.

- Ein Handler, der einen Verweis auf eine Basisklasse des gleichen Typs wie das Ausnahmeobjekt akzeptiert.

- Ein Handler, der einen Verweis auf akzeptiert eine **const** oder **flüchtige** bestehen aus einer Basisklasse des gleichen Typs wie das Ausnahmeobjekt.

- Ein Handler, der einen Zeiger akzeptiert, in den ein ausgelöstes Zeigerobjekt über Standardzeigerkonvertierungsregeln konvertiert werden kann.

Die Reihenfolge, in **catch** -Handlers ist wichtig, da Handler für eine angegebene **versuchen** Block werden überprüft, in der Reihenfolge ihrer Darstellung. Beispielsweise ist es einem Fehler, den Handler einer Basisklasse vor dem Handler einer abgeleiteten Klasse zu platzieren. Nachdem ein entsprechender **catch** Handler gefunden wird, werden nachfolgende Handler nicht überprüft. Als Ergebnis ein Auslassungszeichen **catch** Handler muss der letzte Handler für die **versuchen** Block. Zum Beispiel:

```cpp
// ...
try
{
    // ...
}
catch( ... )
{
    // Handle exception here.
}
// Error: the next two handlers are never examined.
catch( const char * str )
{
    cout << "Caught exception: " << str << endl;
}
catch( CExcptClass E )
{
    // Handle CExcptClass exception here.
}
```

In diesem Beispiel mit den Auslassungspunkten **catch** Handler ist der einzige Handler, der überprüft wird.

## <a name="see-also"></a>Siehe auch

[C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)