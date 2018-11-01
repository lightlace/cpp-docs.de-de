---
title: 'Gewusst wie: Definieren und Verarbeiten von Enumerationen in C++/CLI'
ms.date: 11/04/2016
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
ms.openlocfilehash: 6dc70da0e3888ffee11a6378da5ea82efe58112b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539658"
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>Gewusst wie: Definieren und Verarbeiten von Enumerationen in C++/CLI

In diesem Thema wird erläutert, Enumerationen in C++ / CLI.

## <a name="specifying-the-underlying-type-of-an-enum"></a>Angeben des zugrunde liegende Typs einer Enumeration

Standardmäßig ist der zugrunde liegende Typ einer Enumeration `int`.  Allerdings können Sie angeben, den Typ mit oder ohne Vorzeichen Formen der werden `int`, `short`, `long`, `__int32`, oder `__int64`.  Sie können auch `char`.

```
// mcppv2_enum_3.cpp
// compile with: /clr
public enum class day_char : char {sun, mon, tue, wed, thu, fri, sat};

int main() {
   // fully qualified names, enumerator not injected into scope
   day_char d = day_char::sun, e = day_char::mon;
   System::Console::WriteLine(d);
   char f = (char)d;
   System::Console::WriteLine(f);
   f = (char)e;
   System::Console::WriteLine(f);
   e = day_char::tue;
   f = (char)e;
   System::Console::WriteLine(f);
}
```

**Ausgabe**

```Output
sun
0
1
2
```

## <a name="how-to-convert-between-managed-and-standard-enumerations"></a>Gewusst wie: Konvertieren zwischen verwalteten und Standardenumerationen

Es ist keine standardmäßige Konvertierung zwischen einer Enumeration und einen ganzzahligen Typ. eine Umwandlung ist erforderlich.

```
// mcppv2_enum_4.cpp
// compile with: /clr
enum class day {sun, mon, tue, wed, thu, fri, sat};
enum {sun, mon, tue, wed, thu, fri, sat} day2; // unnamed std enum

int main() {
   day a = day::sun;
   day2 = sun;
   if ((int)a == day2)
   // or...
   // if (a == (day)day2)
      System::Console::WriteLine("a and day2 are the same");
   else
      System::Console::WriteLine("a and day2 are not the same");
}
```

**Ausgabe**

```Output
a and day2 are the same
```

## <a name="operators-and-enums"></a>Operatoren und Enumerationen

Die folgenden Operatoren sind gültig für Enumerationen in C++ / CLI:

|Operator|
|--------------|
|== != \< > \<= >=|
|+ -|
|&#124; ^ & ~|
|++ --|
|sizeof|

Operatoren &#124; ^ & ~ ++--, die nur für die Enumerationen mit ganzzahligem zugrunde liegende Typen, einschließlich nicht "bool" definiert sind.  Beide Operanden müssen von den Enumerationstyp sein.

Der Compiler übernimmt keine statische oder dynamische Prüfung des Ergebnisses einer Enumeration Operation; ein Vorgang möglicherweise nicht in den Bereich der gültigen Enumeratoren der Enumeration einen Wert ab.

> [!NOTE]
>  C ++ 11 stellt die Enum-Klasse-Typen in nicht verwaltetem Code sind grundlegend, als verwaltete Enumerationsklassen in C++ / CLI. Insbesondere der C ++ 11-Enumeration Klassentyp unterstützt nicht die gleichen Operatoren als verwaltete Enumeration Klassentyp in C++ / CLI und C++ / CLI-Quellcode muss bereitstellen, einen Zugriffsspezifizierer in verwaltete Enumeration Klassendeklarationen um sie von nicht verwaltetem (C++ zu unterscheiden 11) Enum Class-Deklarationen. Weitere Informationen zu Enumerationsklassen in C++ / CLI, C++ / CX und C ++ 11 finden Sie unter [Enumerationsklasse](../windows/enum-class-cpp-component-extensions.md).

```
// mcppv2_enum_5.cpp
// compile with: /clr
private enum class E { a, b } e, mask;
int main() {
   if ( e & mask )   // C2451 no E->bool conversion
      ;

   if ( ( e & mask ) != 0 )   // C3063 no operator!= (E, int)
      ;

   if ( ( e & mask ) != E() )   // OK
      ;
}
```

```
// mcppv2_enum_6.cpp
// compile with: /clr
private enum class day : int {sun, mon};
enum : bool {sun = true, mon = false} day2;

int main() {
   day a = day::sun, b = day::mon;
   day2 = sun;

   System::Console::WriteLine(sizeof(a));
   System::Console::WriteLine(sizeof(day2));
   a++;
   System::Console::WriteLine(a == b);
}
```

**Ausgabe**

```Output
4
1
True
```

## <a name="see-also"></a>Siehe auch

[Enumerationsklasse](../windows/enum-class-cpp-component-extensions.md)