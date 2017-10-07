---
title: Enumerationen (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- enum_cpp
dev_langs:
- C++
helpviewer_keywords:
- declarations, enumerations
- enumerators, declaring
- enum keyword [C++]
- named constants, enumeration declarations
- declaring enumerations
ms.assetid: 081829db-5dca-411e-a53c-bffef315bcb3
caps.latest.revision: 27
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5a28ef1a4330f3519a1084921d493b6595f31112
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="enumerations-c"></a>Enumerationen (C++)
Eine Enumeration ist ein benutzerdefinierter Typ, der aus einem Satz von benannten ganzzahligen Konstanten besteht, die als Enumeratoren bezeichnet werden.  
  
> [!NOTE]
>  Dieser Artikel umfasst den `enum`-Typ der ISO-Standardsprache C++ und den bewerteten (oder stark typisierten) `enum class`-Typ, der in C++11 eingeführt wird. Informationen zu den `public enum class` oder `private enum class` Typen in C + c++ / CLI und c++ / CX, finden Sie unter [Enumerationsklasse](../windows/enum-class-cpp-component-extensions.md).  
  
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
  
```  
// Forward declaration of enumerations  (C++11):  
enum A : int; // non-scoped enum must have type specified
enum class B; // scoped enum defaults to int but ...
enum class C : short;  // ... may have any integral underlying type
```  
  
## <a name="parameters"></a>Parameter  
 `identifier`  
 Der Typname, der für die Enumeration angegeben wurde.  
  
 `type`  
 Der zugrunde liegende Typ der Enumeratoren. Alle Enumeratoren weisen den gleichen zugrunde liegenden Typ auf. Kann ein beliebiger ganzzahliger Typ sein.  
  
 `enum-list`  
 Eine durch Trennzeichen getrennte Liste mit Enumeratoren in der Enumeration. Jeder Enumerator oder Variablenname im Bereich muss eindeutig sein. Allerdings können die Werte doppelt vorkommen. In einer Enumeration ohne Bereichseinschränkung ist der Gültigkeitsbereich der umschließende Bereich. In einer bereichsbezogenen Enumeration ist der Bereich selbst die `enum-list`.  In einer bereichsbezogenen Enumeration kann die Liste der wirksamen einen neuen integralen Typ definiert leer sein.
  
 `class`  
 Mit diesem Schlüsselwort in der Deklaration geben Sie an, dass für die Enumeration eine Bereichsbeschränkung gilt, und ein `identifier` muss angegeben werden. Sie können auch das `struct`-Schlüsselwort anstelle von `class` verwenden, da beide in diesem Kontext gleichwertig sind.  
  
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
  
 Jeder Enumerator wird als Konstante behandelt und muss einen eindeutigen Namen innerhalb des Bereichs, in dem `enum` (für Enumerationen ohne Bereichseinschränkung) definiert ist, oder innerhalb der Enumeration selbst (für bereichsbezogene Enumerationen) haben. Die Werte, die für die Namen angegeben werden, müssen nicht eindeutig sein. Wenn z. B. die Deklaration einer Enumeration ohne Bereichseinschränkung `Suit` folgendermaßen ist:  
  
```cpp  
enum Suit { Diamonds = 5, Hearts, Clubs = 4, Spades };  
```  
  
 Dann betragen die Werte von `Diamonds`, `Hearts`, `Clubs` und `Spades` 5, 6, 4 bzw. 5. Beachten Sie, dass 5 mehrmals verwendet wird; dies ist zulässig, auch wenn möglicherweise nicht beabsichtigt. Diese Regeln sind für bereichsbezogene Enumerationen identisch.  
  
 ## <a name="casting-rules"></a>Umwandlungsregeln  
  
 Enumerationskonstanten ohne Bereichseinschränkung können implizit in `int` konvertiert werden, aber ein `int` kann niemals implizit in einen Enumerationswert konvertiert werden. Das folgende Beispiel veranschaulicht, was geschieht, wenn Sie versuchen, `hand` einen Wert zuzuweisen, der nicht `Suit` ist:  
  
```cpp  
int account_num = 135692;  
Suit hand;  
hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'  
  
```  
  
 Eine Umwandlung ist erforderlich, um `int` in einen bereichsbezogenen Enumerator oder einen Enumerator ohne Bereichseinschränkung zu konvertieren. Sie können jedoch einen Enumerator ohne Bereichseinschränkung auch ohne Umwandlung auf einen Ganzzahlwert heraufstufen.  
  
```cpp  
int account_num = Hearts; //OK if Hearts is in a unscoped enum  
```  
  
 Eine solche Verwendung der impliziten Konvertierungen kann zu unbeabsichtigten Nebeneffekten führen. Um Programmierfehler im Zusammenhang mit Enumerationen ohne Bereichseinschränkung zu eliminieren, sind bereichsbezogene Enumerationswerte stark typisiert. Bereichsbezogene Enumeratoren müssen durch den Enumerationstypnamen (Bezeichner) qualifiziert werden und können nicht, wie im folgenden Beispiel gezeigt, implizit konvertiert werden:  
  
```cpp  
namespace ScopedEnumConversions  
{  
    enum class Suit { Diamonds, Hearts, Clubs, Spades };  
  
    void AttemptConversions()  
    {  
        Suit hand;   
        hand = Clubs; // error C2065: 'Clubs' : undeclared identifier  
        hand = Suit::Clubs; //Correct.  
        int account_num = 135692;  
        hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'  
        hand = static_cast<Suit>(account_num); // OK, but probably a bug!!!  
  
        account_num = Suit::Hearts; // error C2440: '=' : cannot convert from 'Suit' to 'int'  
        account_num = static_cast<int>(Suit::Hearts); // OK  
}  
  
```  
  
 Beachten Sie, dass die Zeile `hand = account_num;` noch den Fehler verursacht, der bei Enumerationen ohne Bereichsbeschränkung auftritt, wie oben beschrieben. Sie ist mit einer expliziten Umwandlung zulässig. Bei bereichsbezogenen Enumerationen ist der Versuch einer Konvertierung in der nächsten Anweisung, `account_num = Suit::Hearts;`, nicht mehr ohne eine explizite Umwandlung zulässig. 

## <a name="enums-with-no-enumerators"></a>Enumerationen mit keine Enumeratoren
**Visual Studio 2017 15,3 und höher** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): durch die Definition einer Enumeration (regulären oder Bereichsbezogene) mit einem expliziten zugrunde liegenden Typ und keine Enumeratoren, Sie können faktisch einführen einer neuen integrale eingeben, verfügt über keine implizite Konvertierung in einen anderen Typ aus. Mithilfe dieses Typs statt dessen integrierte zugrunde liegendem Typ kann potenzielle geringfügige Fehler hervorgerufen wurden durch das unbeabsichtigten implizite Konvertierungen ausgelagert wird.  


```cpp
enum class byte : unsigned char { };
```

Der neue Typ ist eine genaue Kopie des zugrunde liegenden Typs und hat daher die gleiche Aufrufkonvention, was bedeutet, dass sie über ABIs ohne Leistungseinbußen verwendet werden kann. Variablen des Typs initialisiert werden, mithilfe von direkten-Listen-Initialisierung ist keine Typumwandlung erforderlich. Das folgende Beispiel zeigt, wie Enumerationen mit keine Enumeratoren in verschiedenen Kontexten initialisieren:

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
 [C-Enumerationsdeklarationen](../c-language/c-enumeration-declarations.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)
