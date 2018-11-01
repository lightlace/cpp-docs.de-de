---
title: Enumerationen (C++)
ms.date: 06/01/2018
f1_keywords:
- enum_cpp
helpviewer_keywords:
- declarations, enumerations
- enumerators, declaring
- enum keyword [C++]
- named constants, enumeration declarations
- declaring enumerations
ms.assetid: 081829db-5dca-411e-a53c-bffef315bcb3
ms.openlocfilehash: 2258683fae8d14051d798cd18a3c3d74f8fdac6d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557976"
---
# <a name="enumerations-c"></a>Enumerationen (C++)

Eine Enumeration ist ein benutzerdefinierter Typ, der aus einem Satz von benannten ganzzahligen Konstanten besteht, die als Enumeratoren bezeichnet werden.

> [!NOTE]
>  Dieser Artikel behandelt die ISO-Standardsprache C++ **Enum** Typ und die Bereichsbezogene (oder stark typisierten) **Enumerationsklasse** Typ, der in C ++ 11 eingeführt wird. Informationen zu den **öffentliche Enumerationsklasse** oder **private Enumerationsklasse** Typen in C++ / CLI und C++ / CX, finden Sie unter [Enumerationsklasse](../windows/enum-class-cpp-component-extensions.md).

## <a name="syntax"></a>Syntax

```
// unscoped enum:
enum [identifier] [: type]
{enum-list}; 

// scoped enum:
enum [class|struct]
[identifier] [: type]
{enum-list};
```

```cpp
// Forward declaration of enumerations  (C++11):
enum A : int; // non-scoped enum must have type specified
enum class B; // scoped enum defaults to int but ...
enum class C : short;  // ... may have any integral underlying type
```

## <a name="parameters"></a>Parameter

*identifier*<br/>
Der Typname, der für die Enumeration angegeben wurde.

*Typ*<br/>
Der zugrunde liegende Typ der Enumeratoren. Alle Enumeratoren weisen den gleichen zugrunde liegenden Typ auf. Kann ein beliebiger ganzzahliger Typ sein.

*Enum-Liste*<br/>
Eine durch Trennzeichen getrennte Liste mit Enumeratoren in der Enumeration. Jeder Enumerator oder Variablenname im Bereich muss eindeutig sein. Allerdings können die Werte doppelt vorkommen. In einer Enumeration ohne bereichseinschränkung ist der Gültigkeitsbereich der umschließende Bereich; in einer bereichsbezogenen Enumeration ist der Bereich ist die *Enumeration-List* selbst.  In einer bereichsbezogenen Enumeration ist kann die Liste leer sein aktiviert einen neuen integralen Typ definiert.

*class*<br/>
Mithilfe dieses Schlüsselwort in der Deklaration können Sie angeben, die Enumeration eine bereichsbeschränkung gilt, und ein *Bezeichner* muss angegeben werden. Sie können auch die **Struktur** -Schlüsselwort anstelle von **Klasse**, wie sie in diesem Kontext semantisch gleichwertig sind.

## <a name="enumerator-scope"></a>Enumerator-Bereich

Eine Enumeration stellt Kontext zum Beschreiben eines Bereichs von Werten bereit, die als benannte Konstanten dargestellt und auch als Enumeratoren bezeichnet werden. In den ursprünglichen C- und C++-Enumerationstypen sind die nicht qualifizierten Enumeratoren überall in dem Bereich sichtbar, in dem die Enumeration deklariert wird. In bereichsbezogenen Enumerationen muss der Enumeratorname durch den Enumerationstypnamen qualifiziert werden. Das folgende Beispiel veranschaulicht diesen grundlegenden Unterschied zwischen den beiden Arten von Enumerationen:

```cpp
namespace CardGame_Scoped
{
    enum class Suit { Diamonds, Hearts, Clubs, Spades };

    void PlayCard(Suit suit)
    {
        if (suit == Suit::Clubs) // Enumerator must be qualified by enum type
        { /*...*/}
    }
}

namespace CardGame_NonScoped
{
    enum Suit { Diamonds, Hearts, Clubs, Spades };

    void PlayCard(Suit suit)
    {
        if (suit == Clubs) // Enumerator is visible without qualification
        { /*...*/
        }
    }
}
```

Jedem Namen in einer Enumeration wird ein ganzzahliger Wert zugewiesen, der seiner Stelle in der Reihenfolge der Werte in der Enumeration entspricht. Standardmäßig wird dem ersten Wert 0, dem nächsten Wert 1 usw. zugewiesen. Sie können jedoch den Wert eines Enumerators explizit festlegen, wie im Folgenden dargestellt:

```cpp
enum Suit { Diamonds = 1, Hearts, Clubs, Spades };
```

Dem Enumerator `Diamonds` wird der Wert `1` zugewiesen. Nachfolgende Enumeratoren erhalten den Wert des vorherigen Enumerators plus eins, wenn ihnen kein expliziter Wert zugeordnet wurde. Im vorherigen Beispiel würde `Hearts` den Wert 2, `Clubs` den Wert 3 usw. erhalten.

Jeder Enumerator wird als Konstante behandelt und müssen einen eindeutigen Namen innerhalb des Bereichs, in denen die **Enum** (für Enumerationen ohne bereichseinschränkung) definiert ist oder innerhalb der **Enum** selbst (für Bereichsbezogene Enumerationen). Die Werte, die für die Namen angegeben werden, müssen nicht eindeutig sein. Wenn z. B. die Deklaration einer Enumeration ohne Bereichseinschränkung `Suit` folgendermaßen ist:

```cpp
enum Suit { Diamonds = 5, Hearts, Clubs = 4, Spades };
```

Dann betragen die Werte von `Diamonds`, `Hearts`, `Clubs` und `Spades` 5, 6, 4 bzw. 5. Beachten Sie, dass 5 mehrmals verwendet wird; dies ist zulässig, auch wenn möglicherweise nicht beabsichtigt. Diese Regeln sind für bereichsbezogene Enumerationen identisch.

## <a name="casting-rules"></a>Umwandlungsregeln

Enumerationskonstanten ohne bereichseinschränkung können implizit konvertiert werden, um **Int**, aber ein **Int** kann niemals implizit in einen Enumerationswert. Das folgende Beispiel veranschaulicht, was geschieht, wenn Sie versuchen, `hand` einen Wert zuzuweisen, der nicht `Suit` ist:

```cpp
int account_num = 135692;
Suit hand;
hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'
```

Eine Umwandlung ist erforderlich, um das Konvertieren einer **Int** auf eine Bereichsbezogene oder ohne bereichseinschränkung Enumerator. Sie können jedoch einen Enumerator ohne Bereichseinschränkung auch ohne Umwandlung auf einen Ganzzahlwert heraufstufen.

```cpp
int account_num = Hearts; //OK if Hearts is in a unscoped enum
```

Eine solche Verwendung der impliziten Konvertierungen kann zu unbeabsichtigten Nebeneffekten führen. Um Programmierfehler im Zusammenhang mit Enumerationen ohne Bereichseinschränkung zu eliminieren, sind bereichsbezogene Enumerationswerte stark typisiert. Bereichsbezogene Enumeratoren müssen durch den Enumerationstypnamen (Bezeichner) qualifiziert werden und können nicht, wie im folgenden Beispiel gezeigt, implizit konvertiert werden:

```cpp
namespace ScopedEnumConversions
{
    enum class Suit { Diamonds, Hearts, Clubs, Spades };

    void AttemptConversions()
    {
        Suit hand; 
        hand = Clubs; // error C2065: 'Clubs' : undeclared identifier
        hand = Suit::Clubs; //Correct.
        int account_num = 135692;
        hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'
        hand = static_cast<Suit>(account_num); // OK, but probably a bug!!!

        account_num = Suit::Hearts; // error C2440: '=' : cannot convert from 'Suit' to 'int'
        account_num = static_cast<int>(Suit::Hearts); // OK
}
```

Beachten Sie, dass die Zeile `hand = account_num;` noch den Fehler verursacht, der bei Enumerationen ohne Bereichsbeschränkung auftritt, wie oben beschrieben. Sie ist mit einer expliziten Umwandlung zulässig. Bei bereichsbezogenen Enumerationen ist der Versuch einer Konvertierung in der nächsten Anweisung, `account_num = Suit::Hearts;`, nicht mehr ohne eine explizite Umwandlung zulässig.

## <a name="no_enumerators"></a> Enumerationen mit keine Enumeratoren

**Visual Studio 2017 Version 15.3 und höher** (verfügbar mit [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): durch Definieren einer Enumeration (reguläre oder Bereichsbezogene) mit einem expliziten zugrunde liegenden Typ und kein Enumeratoren, Sie können in Kraft einführen einer neuen integraler Typ, der verfügt über keine implizite Konvertierung in einen anderen Typ. Dieser Typ wird als integrierte zugrunde liegenden Typs verwenden, können Sie das Fehlerpotenzial feine zurückzuführen, dass unbeabsichtigte impliziten Konvertierungen vermeiden.

```cpp
enum class byte : unsigned char { };
```

Der neue Typ ist eine exakte Kopie des zugrunde liegenden Typs und hat daher dieselbe Aufrufkonvention, was bedeutet, dass sie über ABIs ohne Leistungseinbußen verwendet werden kann. Variablen des Typs initialisiert werden, mithilfe der Direct-List-Initialisierung ist keine Umwandlung erforderlich. Im folgende Beispiel wird veranschaulicht, wie Enumerationen mit keine Enumeratoren in verschiedenen Kontexten initialisiert wird:

```cpp
enum class byte : unsigned char { };

enum class E : int { };
E e1{ 0 };
E e2 = E{ 0 };

struct X
{
    E e{ 0 };
    X() : e{ 0 } { }
};

E* p = new E{ 0 };

void f(E e) {};

int main()
{
    f(E{ 0 });
    byte i{ 42 };
    byte j = byte{ 42 };

    // unsigned char c = j; // C2440: 'initializing': cannot convert from 'byte' to 'unsigned char'
    return 0;
}
```

## <a name="see-also"></a>Siehe auch

[C-Enumerationsdeklarationen](../c-language/c-enumeration-declarations.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)