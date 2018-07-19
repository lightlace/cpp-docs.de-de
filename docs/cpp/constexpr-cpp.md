---
title: Constexpr (C++) | Microsoft Docs
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- constexpr_cpp
dev_langs:
- C++
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f95f6c98138ff1eb52750c1b8593795ca28c784
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417996"
---
# <a name="constexpr-c"></a>constexpr (C++)

Das Schlüsselwort **Constexpr** in C ++ 11 eingeführt und in C ++ 14 verbessert wurde. Es bedeutet *Konstantenausdruck*. Wie **const**, sie können auf Variablen angewendet werden, sodass ein Compilerfehler ausgelöst wird, wenn der Code versucht wird, zum Ändern des Werts. Im Gegensatz zu **const**, **Constexpr** können auch auf Funktionen angewendet werden und Klassenkonstruktoren. **Constexpr** gibt an, dass der Wert oder der Rückgabewert konstant ist und nach Möglichkeit zur Kompilierungszeit berechnet werden wird.

Ein **Constexpr** ganzzahligen Wert kann verwendet werden, wenn eine ganzzahlige Konstante erforderlich ist, z. B. in Vorlagenargumenten und Arraydeklarationen. Und wenn ein Wert zur Kompilierzeit statt zur Laufzeit berechnet werden kann, können sie das Programm schneller ausgeführt und belegen weniger Arbeitsspeicher.

Um die Komplexität der computing Kompilierung Konstanten und deren möglichen Auswirkungen auf die Kompilierungszeit zu beschränken, die C ++ 14-standard erfordert, dass die Konstanten Ausdrücken beteiligten Typen auf beschränkt [Literaltypen](trivial-standard-layout-and-pod-types.md#literal_types).

## <a name="syntax"></a>Syntax

```
constexpr  literal-type  identifier = constant-expression;
constexpr  literal-type  identifier { constant-expression };
constexpr literal-type identifier(params );
constexpr ctor (params);
```

## <a name="parameters"></a>Parameter

 *params*  
Mindestens ein Parameter müssen ein literal sein und müssen selbst sein ein konstanter Ausdruck.

## <a name="return-value"></a>Rückgabewert


 Eine Constexpr-Variable oder Funktion zurückgeben muss eine [Literaltyp](trivial-standard-layout-and-pod-types.md#literal_types).

## <a name="constexpr-variables"></a>constexpr-Variablen

 Der Hauptunterschied zwischen const- und constexpr-Variablen besteht darin, dass die Initialisierung einer const-Variablen bis zur Laufzeit verzögert werden kann, während eine constexpr-Variable zum Zeitpunkt der Kompilierung initialisiert werden muss.  Alle constexpr-Variablen sind auch const.

- Eine Variable deklariert werden kann, mit **Constexpr**, wenn sie über einen Literaltyp verfügt und initialisiert wird. Wenn die Initialisierung von einem Konstruktor ausgeführt wird, muss der Konstruktor deklariert werden, als **Constexpr**.

- Ein Verweis kann als constexpr deklariert werden, wenn das Objekt, auf das er verweist, durch einen konstanten Ausdruck initialisiert wurde und alle impliziten Konvertierungen, die während der Initialisierung aufgerufen werden, auch konstante Ausdrücke sind.

- Alle Deklarationen von einem **Constexpr** Variablen- oder Funktionsname benötigen die **Constexpr** Spezifizierer.

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="constexpr_functions"></a> Constexpr-Funktionen

Ein **Constexpr** Funktion ist eine, deren Rückgabewert zur Kompilierzeit berechnet werden, kann Wenn verwendenden Code erforderlich ist.  Wenn Argumente sind **Constexpr** Werte und verwendete Code den Rückgabewert zum Zeitpunkt der Kompilierung, z. B. zum Initialisieren benötigt eine **Constexpr** Variablen, oder geben Sie ein Nichttyp-Vorlagenargument, es wird eine Kompilierzeitkonstante erzeugt. Bei einem Aufruf mit nicht-**Constexpr** Argumente, oder wenn dessen Wert nicht zum Zeitpunkt der Kompilierung erforderlich ist, erzeugt er einen Wert zur Laufzeit wie eine reguläre Funktion.  (Dieses duale Verhalten erspart Ihnen von schreiben **Constexpr** und nicht-**Constexpr** Versionen der gleichen Funktion.)

Ein **Constexpr** -Funktion oder der Konstruktor ist implizit **Inline**.

Die folgenden Regeln gelten für Constexpr-Funktionen:

- Ein **Constexpr** Funktion muss akzeptieren und zurückgeben nur [Literaltypen](trivial-standard-layout-and-pod-types.md#literal_types).

- Ein **Constexpr** -Funktion kann rekursiv sein.

- Er darf nicht [virtuellen](../cpp/virtual-cpp.md). Ein Konstruktor kann nicht als Constexpr definiert werden, wenn die einschließende Klasse über virtuellen Basisklassen verfügt über.

- Der Text kann definiert werden, als **= Standard** oder **= Löschvorgang durch**.

- Der Text darf nicht **Goto** Anweisungen oder Try-Blöcke.

- Eine explizite Spezialisierung einer nicht-Constexpr-Vorlage kann deklariert werden, als **Constexpr**:

- Eine explizite Spezialisierung einer **Constexpr** Vorlage enthält keinen zudem **Constexpr**:

Die folgenden Regeln gelten für **Constexpr** Funktionen in Visual Studio 2017 und höher:

- Er enthält möglicherweise **Wenn** und **wechseln** Anweisungen und alle Tabellenschleife-Anweisungen, z. B. **für**, bereichsbasierter for, **während**, und **führen-während**.
 
- Deklarationen von lokale Variable kann enthalten, aber die Variable muss initialisiert werden, muss ein literal sein und darf nicht statisch oder Thread-lokal sein. Die lokal deklarierte Variable muss nicht konstant sein und möglicherweise geändert wird.

- Eine Constexpr nicht statische Memberfunktion ist nicht erforderlich, um implizit konstant sein.


```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> Hinweis: In Visual Studio-Debugger beim Debuggen einer nicht optimierten Debugbuild, Sie können feststellen, ob eine **Constexpr** Funktion wird zur Kompilierzeit ausgewertet werden, indem Sie einen Haltepunkt einfügen. Wenn der Haltepunkt erreicht wird, wurde die Funktion zur Laufzeit aufgerufen.  Wenn dies nicht der Fall ist, wurde die Funktion zum Zeitpunkt der Kompilierung aufgerufen.

## <a name="extern-constexpr"></a>"extern" constexpr

Die [/Zc:externConstexpr](../build/reference/zc-externconstexpr.md) -Compileroption bewirkt, dass den Compiler anzuwendende [externe Verknüpfung]() Variablen deklariert, indem **"extern" Constexpr**. In früheren Versionen von Visual Studio, und standardmäßig oder wenn **/Zc:externConstexpr-** angegeben ist, wird Visual Studio wendet interne Verknüpfung zu **Constexpr** Variablen erstellen, selbst wenn die **"extern"** Schlüsselwort verwendet wird. Die **/Zc:externConstexpr** Option ist verfügbar in Visual Studio 2017 Update 15,6 ab. und ist standardmäßig deaktiviert. Die /permissive-option aktiviert /Zc:externConstexpr nicht.

## <a name="example"></a>Beispiel

 Das folgende Beispiel zeigt **Constexpr** Variablen, Funktionen und einen benutzerdefinierten Typ. Beachten Sie, dass in der letzten Anweisung in main() den **Constexpr** Memberfunktion GetValue()"einen Aufruf zur Laufzeit ist, da der Wert nicht erforderlich ist, zum Zeitpunkt der Kompilierung bekannt sein.

```cpp
#include <iostream>

using namespace std;

// Pass by value
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};

// Pass by reference
constexpr float exp2(const float& x, const int& n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp2(x * x, n / 2) :
        exp2(x * x, (n - 1) / 2) * x;
};

// Compile time computation of array length
template<typename T, int N>
constexpr int length(const T(&ary)[N])
{
    return N;
}

// Recursive constexpr function
constexpr int fac(int n)
{
    return n == 1 ? 1 : n*fac(n - 1);
}

// User-defined type
class Foo
{
public:
    constexpr explicit Foo(int i) : _i(i) {}
    constexpr int GetValue()
    {
        return _i;
    }
private:
    int _i;
};

int main()
{
    //foo is const:
    constexpr Foo foo(5);
    // foo = Foo(6); //Error!

    //Compile time:
    constexpr float x = exp(5, 3);
    constexpr float y { exp(2, 5) };
    constexpr int val = foo.GetValue();
    constexpr int f5 = fac(5);
    const int nums[] { 1, 2, 3, 4 };
    const int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };

    //Run time:
    cout << "The value of foo is " << foo.GetValue() << endl;

}

```

## <a name="requirements"></a>Anforderungen

Visual Studio 2015

## <a name="see-also"></a>Siehe auch

- [Deklarationen und Definitionen](../cpp/declarations-and-definitions-cpp.md)
- [const](../cpp/const-cpp.md)
