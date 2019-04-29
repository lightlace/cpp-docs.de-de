---
title: Überladen des &gt;&gt;-Operators für eigene Klassen
ms.date: 11/04/2016
helpviewer_keywords:
- operator>>
- operator>>, overloading for your own classes
- operator >>, overloading for your own classes
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
ms.openlocfilehash: 86b8af963345c8eb9b3f44cfb16332bc09420bf3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370722"
---
# <a name="overloading-the-gtgt-operator-for-your-own-classes"></a>Überladen des &gt;&gt;-Operators für eigene Klassen

Eingabestreams verwenden die Extraktion (`>>`)-Operator für die Standardtypen. Sie können ähnliche Extraktionsoperatoren für eigene Typen schreiben. Der Erfolg hängt von der genauen Nutzung von Leerraum ab.

Hier ist ein Beispiel für einen Extraktionsoperator der `Date`-Klasse, wie vorher beschrieben:

```cpp
istream& operator>> (istream& is, Date& dt)
{
    is>> dt.mo>> dt.da>> dt.yr;
    return is;
}
```

## <a name="see-also"></a>Siehe auch

[Eingabestreams](../standard-library/input-streams.md)<br/>
