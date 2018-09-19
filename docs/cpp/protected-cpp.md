---
title: geschützt (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- protected_cpp
dev_langs:
- C++
helpviewer_keywords:
- protected keyword [C++], member access
- protected keyword [C++]
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9dd04b902c5210978a36a6075803b836f01c9da7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068532"
---
# <a name="protected-c"></a>protected (C++)

## <a name="syntax"></a>Syntax

```
protected:
   [member-list]
protected base-class
```

## <a name="remarks"></a>Hinweise

Die **geschützt** -Schlüsselwort spezifiziert den Zugriff auf Klassenmember in der *Memberliste* bis zum nächsten Zugriffsspezifizierer (**öffentliche** oder **Private**) oder das Ende der Klassendefinition. Klassenmember deklariert als **geschützt** kann nur mit folgenden verwendet werden:

- Memberfunktionen der Klasse, die ursprünglich diese Member deklariert hat.

- Friends der Klasse, die ursprünglich diese Member deklariert hat.

- Klassen, die mit öffentlichem oder geschütztem Zugriff von der Klasse abgeleitet werden, die ursprünglich diese Member deklariert hat.

- Direkt privat abgeleitete Klassen, die auch über privaten Zugriff auf geschützte Member verfügen.

Wenn Sie den Namen einer Basisklasse vorangestellt der **geschützt** Schlüsselwort Gibt an, dass die öffentlichen und geschützten Member der Basisklasse geschützte Member der abgeleiteten Klassen.

Geschützte Member sind nicht so privat wie **private** Elemente, die nur für Member der Klasse zugegriffen werden, in dem sie deklariert werden, aber sie sind nicht so öffentlich wie **öffentliche** Elemente, die in zugegriffen werden kann jede Funktion.

Geschützte Member, die auch als deklariert werden **statische** für alle Funktionen Friend- oder Memberfunktionen einer abgeleiteten Klasse zugegriffen werden. Geschützte Member, die nicht als deklariert sind **statische** für Friends- und Memberfunktionen in einer abgeleiteten Klasse nur über einen Zeiger / Verweis oder eine Objekt der abgeleiteten Klasse zugänglich sind.

Weitere Informationen finden Sie unter [Friend](../cpp/friend-cpp.md), [öffentliche](../cpp/public-cpp.md), [private](../cpp/private-cpp.md), und der memberzugriffstabelle in [Steuern des Zugriffs auf Klassenmember](member-access-control-cpp.md) .

## <a name="clr-specific"></a>"/clr"-spezifisch

In CLR-Typen, die C++ Schlüsselwörter für Zugriffsspezifizierer zugreifen (**öffentliche**, **private**, und **geschützt**) kann die Sichtbarkeit von Typen und Methoden hinsichtlich der Assemblys beeinträchtigen. Weitere Informationen finden Sie unter [Memberzugriffssteuerung](member-access-control-cpp.md).

> [!NOTE]
>  Dateien mit kompiliert [/ln](../build/reference/ln-create-msil-module.md) durch dieses Verhalten nicht betroffen sind. In diesem Fall werden alle verwalteten Klassen (entweder "public" oder "private") angezeigt.

## <a name="end-clr-specific"></a>"/clr"-spezifisch – Ende

## <a name="example"></a>Beispiel

```cpp
// keyword_protected.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class X {
public:
   void setProtMemb( int i ) { m_protMemb = i; }
   void Display() { cout << m_protMemb << endl; }
protected:
   int  m_protMemb;
   void Protfunc() { cout << "\nAccess allowed\n"; }
} x;

class Y : public X {
public:
   void useProtfunc() { Protfunc(); }
} y;

int main() {
   // x.m_protMemb;         error, m_protMemb is protected
   x.setProtMemb( 0 );   // OK, uses public access function
   x.Display();
   y.setProtMemb( 5 );   // OK, uses public access function
   y.Display();
   // x.Protfunc();         error, Protfunc() is protected
   y.useProtfunc();      // OK, uses public access function
                        // in derived class
}
```

## <a name="see-also"></a>Siehe auch

[Steuern des Zugriffs auf Klassenmember](member-access-control-cpp.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)