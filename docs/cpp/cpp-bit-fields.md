---
title: C++-Bitfelder | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- bitfields [C++]
- fields [C++], bit
- bit fields
ms.assetid: 6f4b62e3-cc1d-4e5d-bf34-05904104f71a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4dcfd93d1529844c7e5b72d61a6f1fd87d6dd3a7
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940435"
---
# <a name="c-bit-fields"></a>C++-Bitfelder

Klassen und Strukturen können Member enthalten, die weniger Speicher als ein ganzzahliger Typ belegen. Diese Member werden als Bitfelder angegeben. Die Syntax für Bitfeld *Member-Declarator* Spezifikation folgt:

## <a name="syntax"></a>Syntax

*Deklarator* **:** *konstanter Ausdruck*

## <a name="remarks"></a>Hinweise

Der (optionale) *Deklarator* ist der Name, mit dem das Element in der Anwendung erfolgt. Es muss ein ganzzahliger Typ sein (einschließlich Enumerationstypen). Die *Konstantenausdruck* gibt die Anzahl der Bits, die das Element befindet sich in der Struktur an. Anonyme Bitfelder, also Bitfeldmember ohne Bezeichner, können zur Auffüllung verwendet werden.

> [!NOTE]
> Ein unbenanntes Bitfeld der Breite 0 erzwingt die Ausrichtung des nächsten Bitfelds an den nächsten **Typ** Grenze, in denen **Typ** ist der Typ des Members.

 Das folgende Beispiel deklariert eine Struktur, die zwei Bitfelder enthält:

```cpp
// bit_fields1.cpp
// compile with: /LD
struct Date {
   unsigned short nWeekDay  : 3;    // 0..7   (3 bits)
   unsigned short nMonthDay : 6;    // 0..31  (6 bits)
   unsigned short nMonth    : 5;    // 0..12  (5 bits)
   unsigned short nYear     : 8;    // 0..100 (8 bits)
};
```

Das konzeptionelle Speicherlayout eines Objekts vom Typ `Date` wird in der folgenden Abbildung dargestellt.

![Speicherlayout eines Datumsobjekts](../cpp/media/vc38uq1.png "vc38UQ1") Layout des Datumsobjekts Arbeitsspeicher

Beachten Sie, dass `nYear` 8 Bit lang und verursacht einen Überlauf der Wortgrenze des deklarierten Typs, **ohne Vorzeichen** **kurze**. Aus diesem Grund ist es am Anfang eines neuen begonnen **ohne Vorzeichen** **kurze**. Es ist nicht notwendig, dass alle Bitfelder in ein Objekt des zugrunde liegenden Typs passen. Neue Speichereinheiten werden entsprechend der Anzahl von Bits, die in der Deklaration angefordert werden, zugeordnet.

**Microsoft-spezifisch**

Die Daten, die als Bitfelder deklariert werden, werden beginnend mit dem niedrigsten Bitwert bis hin zum höchsten Bitwert aufgeführt, wie in der Abbildung oben dargestellt.

**Ende Microsoft-spezifisch**

Wenn die Deklaration einer Struktur ein unbenanntes Feld mit der Länge 0 (null) enthält, wie im folgenden Beispiel gezeigt,

```cpp
// bit_fields2.cpp
// compile with: /LD
struct Date {
   unsigned nWeekDay  : 3;    // 0..7   (3 bits)
   unsigned nMonthDay : 6;    // 0..31  (6 bits)
   unsigned           : 0;    // Force alignment to next boundary.
   unsigned nMonth    : 5;    // 0..12  (5 bits)
   unsigned nYear     : 8;    // 0..100 (8 bits)
};
```

das Speicherlayout ist dann in der folgenden Abbildung dargestellt:

![Layout des Datumsobjekts mit 0 (null)&#45;Bitfeld der Länge](../cpp/media/vc38uq2.png "vc38UQ2") Layout des Datumsobjekts mit Bitfeld der Länge 0 (null)

Der zugrunde liegende Typ eines Bitfelds muss ein ganzzahliger Typ sein, wie in beschrieben [Basistypen](../cpp/fundamental-types-cpp.md).

Wenn die Initialisierung für einen Verweis vom Typ `const T&` ist ein l-Wert, der auf ein Bitfeld vom Typ verweist `T`, der Verweis wird nicht direkt an das Bitfeld gebunden. Stattdessen wird der Verweis in ein temporäres initialisiert, um den Wert des Bitfelds gebunden.

## <a name="restrictions-on-bit-fields"></a>Einschränkungen bei Bitfeldern

Die folgende Liste zeigt Einzelheiten zu fehlerhaften Operationen in Bitfeldern:

- Verwenden der Adresse eines Bitfelds.

- Initialisieren von einer nicht -**const** Verweis mit einem Bitfeld.

## <a name="see-also"></a>Siehe auch

- [Klassen und Strukturen](../cpp/classes-and-structs-cpp.md)
