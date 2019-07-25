---
title: Überladen des &lt;&lt;-Operators für eigene Klassen
ms.date: 11/04/2016
helpviewer_keywords:
- operator<<, overloading for your own classes
- operator <<, overloading for your own classes
ms.assetid: ad1d2c49-d84e-48a8-9c09-121f28b10bf0
ms.openlocfilehash: c470bb7335a5997ae26327f99b8c5f31d20b4edb
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452055"
---
# <a name="overloading-the-ltlt-operator-for-your-own-classes"></a>Überladen des &lt;&lt;-Operators für eigene Klassen

Eingabestreams verwenden die Extraktion (`<<`)-Operator für die Standardtypen. Sie können auch den `<<`-Operator für eigene Klassen überladen.

## <a name="example"></a>Beispiel

Die `write`-Beispielfunktion zeigt die Verwendung einer `Date`-Struktur. Ein Datum ist ein idealer Kandidat für eine C++-Klasse, in der Datenmember (Monat, Tag und Jahr) aus der Ansicht ausgeblendet werden. Ein Ausgabestream ist das logische Ziel für die Anzeige einer solchen Struktur. Dieser Code zeigt ein Datum unter Verwendung des `cout`-Objekts:

```cpp
Date dt(1, 2, 92);

cout <<dt;
```

Damit `cout` ein `Date`-Objekt nach den Einfügeoperator akzeptiert, müssen Sie den Einfügeoperator zum Erkennen eines `ostream`-Objekts auf der linken Seite und eines `Date`-Objekts auf der rechten Seite überladen. Die überladenen `<<` Operatorfunktion muss dann als Friend der Klasse `Date` deklariert werden, sodass sie mit einem `Date`-Objekt auf die privaten Daten zugreifen kann.

```cpp
// overload_date.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

class Date
{
    int mo, da, yr;
public:
    Date(int m, int d, int y)
    {
        mo = m; da = d; yr = y;
    }
    friend ostream& operator<<(ostream& os, const Date& dt);
};

ostream& operator<<(ostream& os, const Date& dt)
{
    os << dt.mo << '/' << dt.da << '/' << dt.yr;
    return os;
}

int main()
{
    Date dt(5, 6, 92);
    cout << dt;
}
```

```Output
5/6/92
```

## <a name="remarks"></a>Hinweise

Der überladene Operator gibt einen Verweis auf das ursprüngliche `ostream`-Objekt zurück, d.h., Sie können Einfügevorgängen kombinieren:

```cpp
cout <<"The date is" <<dt <<flush;
```

## <a name="see-also"></a>Siehe auch

[Ausgabestreams](../standard-library/output-streams.md)
