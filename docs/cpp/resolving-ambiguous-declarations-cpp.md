---
title: Auflösen mehrdeutiger Deklarationen (C++)
ms.date: 11/04/2016
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
ms.openlocfilehash: 52e94f474d59505298cb4f78a477cedd21b90aad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403398"
---
# <a name="resolving-ambiguous-declarations-c"></a>Auflösen mehrdeutiger Deklarationen (C++)

Um explizite Konvertierungen von einem Typ zum anderen auszuführen, müssen Sie die Umwandlungen verwenden, die den angestrebten Typnamen angeben. Einige Typumwandlungen führen zu einer syntaktischen Mehrdeutigkeit. Die folgenden Typumwandlungen in Funktionstypen sind mehrdeutig:

```cpp
char *aName( String( s ) );
```

Es ist unklar, ob es sich um eine Funktionsdeklaration oder eine Objektdeklaration mit einer Umwandlung im Funktionsstil als Initialisierer handelt: Es kann eine Funktion, die Rückgabe von Typ deklariert `char *` , akzeptiert ein Argument vom Typ `String`, oder deklarieren sie das Objekt `aName` und initialisieren Sie es mit dem Wert des `s` Umwandlung zum Typ `String`.

Wenn eine Deklaration als eine gültige Funktionsdeklaration betrachtet werden kann, wird sie als solche behandelt. Nur wenn sie keine Funktionsdeklaration sein kann – d. h., wenn sie syntaktisch falsch wäre – wird eine Anweisung daraufhin überprüft, ob sie eine Funktionsformattypumwandlung ist. Daher betrachtet der Compiler die Anweisung als Deklaration einer Funktion und ignoriert die Klammern um den `s`-Bezeichner. Andererseits sind die Anweisungen

```cpp
char *aName( (String)s );
```

und

```cpp
char *aName = String( s );
```

sind eindeutig Deklarationen von Objekten und eine benutzerdefinierte Konvertierung von Typ `String` eingeben `char *` wird aufgerufen, um die Initialisierung von `aName`.