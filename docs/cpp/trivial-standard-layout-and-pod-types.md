---
title: Trivial, Standardlayout-POD und Literaltypen
ms.date: 04/05/2018
ms.assetid: 2b23a7be-9bad-49fc-8298-31a9a7c556b0
ms.openlocfilehash: c742f4c84a1b2ba558b790d7eea7760902da7818
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51521699"
---
# <a name="trivial-standard-layout-pod-and-literal-types"></a>Trivial, Standardlayout-POD und Literaltypen

Der Begriff *Layout* bezieht sich auf wie die Member eines Objekts der Klasse, Struktur oder union-Typ im Arbeitsspeicher angeordnet werden. In einigen Fällen ist das Layout klar definierte, durch die Language-Spezifikation. Wenn eine Klasse oder Struktur bestimmte C++-Sprachfeatures wie virtuelle Basisklassen, die virtuelle Funktionen, die Mitglieder mit anderen Access Control enthält, klicken Sie dann der Compiler ist jedoch ein Layout auswählen. Das Layout kann variieren, je nachdem, welche Optimierungen ausgeführt werden, und in vielen Fällen möglicherweise Objekt einen zusammenhängenden Bereich des Arbeitsspeichers nicht selbst belegt. Wenn eine Klasse virtuelle Funktionen verfügt, können alle Instanzen dieser Klasse z. B. eine einzelne virtuelle Funktionstabelle freigeben. Solche Typen werden natürlich sehr nützlich, aber sie haben auch Einschränkungen. Da das Layout nicht definiert ist. können nicht sie auf Programme, die in anderen Sprachen wie z. B. C, geschrieben übergeben werden, und da sie nicht zusammenhängende möglicherweise nicht zuverlässig kopiert werden mit schnellen Low-Level-Funktionen wie z. B. `memcopy` oder über ein Netzwerk serialisiert.

Damit können Compiler als auch C++-Programmen und Metaprograms Grund bezüglich der Eignung eines beliebigen angegebenen Typs für Vorgänge, die von einer bestimmten Speicherlayout abhängen, C ++ 14 drei Kategorien von einfachen Klassen und Strukturen eingeführt: *trivial*, *Standardlayout-*, und *POD* oder Plain Old Data. Die Standardbibliothek hat die Funktionsvorlagen `is_trivial<T>`, `is_standard_layout<T>` und `is_pod<T>` , die bestimmen, ob ein bestimmtes Typs zu einer bestimmten Kategorie gehört.

## <a name="trivial-types"></a>Einfache Typen

Wenn eine Klasse oder Struktur in C++ hat der Compiler bereitgestellten, oder explizit auf den Standardwert festgelegte spezielle Memberfunktionen ist es ein einfacher Typ. Es nimmt einen zusammenhängenden Bereich ein. Sie können Elemente mit verschiedenen Zugriffsspezifizierer haben. In C++ kann der Compiler wie Anordnen der Elemente in diesem Fall werden soll. Aus diesem Grund können Sie Memcopy solche Objekte, aber Sie können nicht zuverlässig nutzen müssen, von einem C-Programm. Ein einfacher Typ T kann in ein Array von Char "oder" unsigned Char kopiert, und sicher wieder in einer T-Variablen kopiert werden. Beachten Sie, dass aufgrund der ausrichtungsanforderungen, kann es Auffüll-Bytes zwischen Typmember.

Einfache Typen haben einen trivialen Standardkonstruktor trivialen Kopierkonstruktor, Kopierzuweisungsoperator und trivialen Destruktor. In jedem Fall *trivial* bedeutet, dass der Konstruktor/Operator/Destruktor ist nicht vom Benutzer bereitgestellte und gehört zu einer Klasse mit

- keine virtuellen Funktionen oder der virtuellen Basisklassen

- keine Basisklassen mit einem entsprechenden nicht trivialen Konstruktor/Operator/Destruktor

- Geben Sie keine Datenmember der Klasse mit einem entsprechenden nicht trivialen Konstruktor/Operator/Destruktor

Die folgenden Beispiele zeigen, einfache Typen. In Trivial2, das Vorhandensein der `Trivial2(int a, int b)` -Konstruktor erfordert, dass Sie über einen Standardkonstruktor bereitstellen. Für den Typ um als einfach zu gelten müssen Sie diesen Konstruktor explizit Standard.

```cpp
struct Trivial
{
      int i;
private:
   int j;
   };

struct Trivial2
{
   int i;
   Trivial2(int a, int b) : i(a), j(b) {}
   Trivial2() = default;
   private:
   int j;   // Different access control
};
```

## <a name="standard-layout-types"></a>Standardlayout-Typen

Wenn eine Klasse oder Struktur enthält keine bestimmte Funktionen der Programmiersprache C++ wie z. B. virtuelle Funktionen, die in der Programmiersprache C nicht gefunden werden, und alle Elemente verfügen über die gleichen Access Control, ist es ein Standardlayout. Memcopy-fähig ist, und das Layout wird ausreichend definiert, dass sie von C-Programmen verwendet werden kann. Standardlayout-können spezielle Memberfunktionen aufweisen. Standardlayout Typen haben außerdem folgende Eigenschaften:

- keine virtuellen Funktionen oder die virtuelle Basisklassen

- alle nicht statischen Datenmember haben die gleichen Access control

- alle nicht statischen Member des Klassentyps sind Standard-layout

- Basisklassen sind Standard-layout

- verfügt über keine Basisklassen des gleichen Typs wie der erste nicht statische Datenmember aus.

- trifft eine der folgenden Bedingungen:

  - keine nicht statischen Datenmember in der am stärksten abgeleiteten Klasse und nicht mehr als einer Basisklasse mit nicht statischen Datenmember, oder

  - verfügt über keine Basisklassen mit nicht statischen Datenmember

Der folgende Code zeigt ein Beispiel für einen Standard-Layout-Typ:

```cpp
struct SL
{
   // All members have same access:
   int i;
   int j;
   SL(int a, int b) : i(a), j(b) {} // User-defined constructor OK
};
```

Die letzten beiden Anforderungen können vielleicht besser mit Code dargestellt werden. Im nächsten Beispiel, obwohl Basis ist Standardlayout, `Derived` ist nicht Standardlayout, da beide It (die am stärksten abgeleitete Klasse) und `Base` nicht statischen Datenmember aufweisen:

```cpp
struct Base
{
   int i;
   int j;
};

// std::is_standard_layout<<Derived> == false!
struct Derived : public Base
{
   int x;
   int y;
};
```

In diesem Beispiel `Derived` Standardlayout-ist da `Base` verfügt über keine nicht statischen Datenmember:

```cpp
struct Base
{
   void Foo() {}
};

// std::is_standard_layout<<Derived> == true
struct Derived : public Base
{
   int x;
   int y;
};
```

Abgeleitete wäre auch Standardlayout-Wenn `Base` hatte die Datenmember und `Derived` mussten nur die Member-Funktionen.

## <a name="pod-types"></a>POD-Typen

Wenn eine Klasse oder Struktur sowohl einfache als auch Standardlayout-ist, ist es ein POD (Plain Old Data)-Typ. Das Speicherlayout der POD-Typen ist daher zusammenhängenden, und jedes Element verfügt über eine höhere Adresse als die Member, die davor, deklariert wurde, sodass Byte für Byte kopiert und binäre e/a für diese Typen ausgeführt werden können.  Skalare Typen wie Int sind auch die POD-Typen. POD-Typen, die Klassen sind, können nur POD-Typen als nicht statischen Datenmember besitzen.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die Unterschiede zwischen trivial, Standardlayout- und einfache Typen:

```cpp
#include <type_traits>
#include <iostream>

using namespace std;

struct B
{
protected:
   virtual void Foo() {}
};

// Neither trivial nor standard-layout
struct A : B
{
      int a;
   int b;
   void Foo() override {} // Virtual function
};

// Trivial but not standard-layout
struct C
   {
      int a;
private:
   int b;   // Different access control
};

// Standard-layout but not trivial
struct D
{
   int a;
   int b;
   D() {} //User-defined constructor
};

struct POD
{
   int a;
   int b;
};

int main()
{
   cout << boolalpha;
   cout << "A is trivial is " << is_trivial<A>() << endl; // false
   cout << "A is standard-layout is " << is_standard_layout<A>() << endl;  // false

   cout << "C is trivial is " << is_trivial<C>() << endl; // true
   cout << "C is standard-layout is " << is_standard_layout<C>() << endl;  // false

   cout << "D is trivial is " << is_trivial<D>() << endl;  // false
   cout << "D is standard-layout is " << is_standard_layout<D>() << endl; // true

   cout << "POD is trivial is " << is_trivial<POD>() << endl; // true
   cout << "POD is standard-layout is " << is_standard_layout<POD>() << endl; // true

   return 0;
}
```

## <a name="literal_types"></a> Literaltypen

Das Layout eines Literaltyps kann zur Kompilierzeit bestimmt werden. Folgende Typen sind Literaltypen:

- void
- Skalare Typen
- references
- Void-Arrays, skalare Typen oder Verweise
- Eine Klasse, die einen trivialen Destruktor und einen oder mehrere constexpr-Konstruktoren aufweist, die keine Konstruktoren zum Verschieben oder Kopieren sind. Darüber hinaus müssen alle nicht statischen Datenmember und Basisklassen Literaltypen und permanent sein.

## <a name="see-also"></a>Siehe auch

[Grundlegende Konzepte](../cpp/basic-concepts-cpp.md)