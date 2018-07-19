---
title: Trivial, Standardlayout- und POD Literaltypen | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.topic: language-reference
ms.assetid: 2b23a7be-9bad-49fc-8298-31a9a7c556b0
ms.openlocfilehash: 7a80db109df1d9aa25f471312a9ff7103b90df7b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32424850"
---
# <a name="trivial-standard-layout-pod-and-literal-types"></a>Trivial, Standardlayout- und POD Literaltypen

Der Begriff *Layout* bezieht sich auf wie die Member eines Objekts von der Klasse, Struktur oder union-Typs im Arbeitsspeicher angeordnet sind. In einigen Fällen wird das Layout klar definierten, von der Language-Spezifikation. Wenn eine Klasse oder Struktur bestimmter C++-Sprachfeatures wie virtuelle Basisklassen, virtuelle Funktionen, Member mit verschiedenen Zugriffssteuerung enthält, klicken Sie dann der Compiler ist jedoch frei, um ein Layout auswählen. Das Layout kann variieren, je nachdem, welche Optimierungen durchgeführt werden, und in vielen Fällen möglicherweise Objekt einen zusammenhängenden Bereich des Arbeitsspeichers nicht selbst belegen. Z. B. können eine Klasse virtuelle Funktionen verfügt, alle Instanzen dieser Klasse eine einzelne virtuelle Funktionstabelle freigeben. Solche Typen sind natürlich sehr nützlich, aber sie weisen auch Einschränkungen. Da das Layout undefiniert ist können nicht sie auf Programme, die in anderen Sprachen wie C#, geschrieben übergeben werden, und da sie nicht zusammenhängend sein könnten sie können nicht zuverlässig kopiert werden mit fast Low-Level-Funktionen wie z. B. `memcopy` oder über ein Netzwerk serialisiert.

 Um den Compiler als auch C++-Programmen und Metaprograms auf Grund bezüglich der Eignung eines angegebenen Typs für Vorgänge, die von einer bestimmten Speicherlayout abhängen aktivieren möchten, C ++ 14 drei Kategorien von einfachen Klassen und Strukturen eingeführt: *trivial*, *Standardlayout-*, und *POD* oder Plain Old Data. Die Standardbibliothek hat die Funktionsvorlagen `is_trivial<T>`, `is_standard_layout<T>` und `is_pod<T>` , die bestimmen, ob ein bestimmten Typs zu einer bestimmten Kategorie gehört.

## <a name="trivial-types"></a>Einfache Typen

 Wenn eine Klasse oder Struktur in C++ Compiler bereitgestellten hat, oder explizit vorgegebene spezielle Memberfunktionen ist es ein einfacher Typ ist. Er nimmt einen zusammenhängenden Bereich ein. Sie können mit verschiedenen Zugriffsspezifizierer Elemente haben. In C++ kann der Compiler zum Anordnen der Elemente in dieser Situation auswählen. Deshalb können Sie Memcopy solche Objekte, aber Sie können nicht zuverlässig nutzen müssen, aus einem C-Programm. Ein einfacher Typ T kann in ein Array von Char "oder" unsigned Char kopiert, und sicher in einer T-Variablen zurück kopiert werden. Beachten Sie, dass aufgrund der ausrichtungsanforderungen, kann es Auffüll-Bytes zwischen Typmember.

 Einfache Typen haben einen trivialen Standardkonstruktor trivialen Kopierkonstruktor, Kopierzuweisungsoperator und trivialen Destruktor. In jedem Fall *trivial* bedeutet, dass der Konstruktor/Operator/Destruktor ist nicht vom Benutzer bereitgestellte und gehört zu einer Klasse mit

- keine virtuellen Funktionen oder der virtuelle Basisklassen

- keine Basisklassen mit einem entsprechenden nicht trivialen Konstruktor/Operator/Destruktor

- keine Datenmember des Klassentyps mit einem entsprechenden nicht trivialen Konstruktor/Operator/Destruktor

Die folgenden Beispiele zeigen, einfache Typen. In Trivial2, das Vorhandensein der `Trivial2(int a, int b)` Konstruktor erfordert, dass Sie einen Standardkonstruktor bereitstellen. Für den Typ als triviale zu qualifizieren müssen Sie diesen Konstruktor explizit standardmäßig.

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

## <a name="standard-layout-types"></a>Standardlayout Typen

 Wenn eine Klasse oder Struktur enthält keine bestimmte C++-Sprachfunktionen wie virtuelle Funktionen, die nicht in der Programmiersprache C enthalten sind, und alle Elemente verfügen über die gleichen Zugriffssteuerung, ist es ein Standardlayout. Memcopy-fähig ist, und das Layout ausreichend definiert, die sie von C-Programmen verwendet werden kann. Standardlayout-können spezielle Memberfunktionen aufweisen. Darüber hinaus haben Standardlayout Typen folgende Eigenschaften:

- keine virtuellen Funktionen oder virtuelle Basisklassen

- alle nicht statischen Datenmember haben die gleichen Zugriffssteuerung

- alle nicht statischen Member des Klassentyps werden Standardlayout-

- Alle Basisklassen sind Standard-layout

- wurde keine Basis-Klassen den gleichen Typ wie der erste nicht statische Datenmember.

- erfüllt eine der folgenden Bedingungen:

  - keine nicht statischen Datenmember in den meisten abgeleiteten Klasse und nicht mehr als einer Basisklasse mit nicht statischen Datenmember, oder

  - wurde keine Basis-Klassen nicht statischen Datenmember

Der folgende Code zeigt ein Beispiel für einen Typ Standardlayout-:

```cpp
struct SL
{
   // All members have same access:
   int i;
   int j;
   SL(int a, int b) : i(a), j(b) {} // User-defined constructor OK
};

```

 Die letzten beiden Anforderungen können durch Code möglicherweise besser dargestellt werden. Im nächsten Beispiel wird Base, obwohl Standardlayout-, `Derived` ist nicht Standardlayout, da beide It (die am stärksten abgeleitete Klasse) und `Base` nicht statischen Datenmember aufweisen:

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

 Abgeleitete wäre auch Standardlayout-Wenn `Base` hatte den Datenmember und `Derived` nur Memberfunktionen hatte.

## <a name="pod-types"></a>POD-Typen

 Wenn eine Klasse oder Struktur trivial und Standardlayout-ist, ist es ein POD (Plain Old Data)-Typ. Das Speicherlayout der POD-Typen aus diesem Grund zusammenhängend ist, und jedes Element verfügt über eine höhere Adresse als der Member, die davor, deklariert wurde, sodass Byte für Byte kopiert und binäre e/a für diese Typen ausgeführt werden können.  Skalare Typen wie Int sind auch POD-Typen. POD-Typen, die Klassen sind, dürfen nur POD-Typen als nicht statischen Datenmember enthalten.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die Unterschiede zwischen trivial, Standardlayout- und POD-Typen:

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
- Referenzen
- Void-Arrays, skalare Typen oder Verweise
- Eine Klasse, die einen trivialen Destruktor und einen oder mehrere constexpr-Konstruktoren aufweist, die keine Konstruktoren zum Verschieben oder Kopieren sind. Darüber hinaus müssen alle nicht statischen Datenmember und Basisklassen Literaltypen und permanent sein.

## <a name="see-also"></a>Siehe auch

 [Grundlegende Konzepte](../cpp/basic-concepts-cpp.md)