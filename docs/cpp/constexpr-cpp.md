---
title: constexpr (C++)
ms.date: 08/05/2019
f1_keywords:
- constexpr_cpp
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
ms.openlocfilehash: 5c98436f537b34b1c9050e057971938d48792db1
ms.sourcegitcommit: c3bf94210bdb73be80527166264d49e33784152c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2019
ms.locfileid: "68821097"
---
# <a name="constexpr-c"></a>constexpr (C++)

Das Schlüsselwort " **constexpr** " wurde in c++ 11 eingeführt und in "c++ 14" verbessert. Es bedeutet *konstanter Ausdruck*. Wie bei **Konstanten**können Sie auch auf Variablen angewendet werden, sodass ein Compilerfehler ausgelöst wird, wenn ein Code versucht, den Wert zu ändern. Im Gegensatz zu **const**kann **constexpr** auch auf Funktionen und Klassenkonstruktoren angewendet werden. **constexpr** gibt an, dass der Wert oder der Rückgabewert konstant ist und, wenn möglich, zur Kompilierzeit berechnet wird.

Ein ganzzahliger **constexpr** -Wert kann überall dort verwendet werden, wo eine const-Ganzzahl erforderlich ist, beispielsweise in Vorlagen Argumenten und Array Deklarationen. Wenn ein Wert zur Kompilierzeit anstelle der Laufzeit berechnet werden kann, kann er das Programm schneller ausführen und weniger Arbeitsspeicher verbrauchen.

Um die Komplexität der Konstanten für die Kompilierzeit Konstante und deren potenzielle Auswirkung auf die Kompilierungszeit einzuschränken, erfordert der c++ 14-Standard, dass die Typen in konstanten Ausdrücken [Literaltypen](trivial-standard-layout-and-pod-types.md#literal_types)sind.

## <a name="syntax"></a>Syntax

> **"constexpr"** *Literal-Typ* *Bezeichner* **=** *Konstantenausdruck* **;** 
>  **"constexpr"** *Literal-Typ* *Bezeichner* **{** *konstanter Ausdruck* **}** **;** 
>  **"constexpr"** *Literal-Typ* *Bezeichner* **(** *Params* **)** **;** 
>  **"constexpr"** *"ctor"* **(** *Params* **)** **;**

## <a name="parameters"></a>Parameter

*params*<br/>
Ein oder mehrere Parameter, von denen jeder ein Literaltyp sein muss und selbst ein konstanter Ausdruck sein muss.

## <a name="return-value"></a>Rückgabewert

Eine constexpr-Variable oder-Funktion muss einen [Literaltyp](trivial-standard-layout-and-pod-types.md#literal_types)zurückgeben.

## <a name="constexpr-variables"></a>constexpr-Variablen

Der Hauptunterschied zwischen const-und constexpr-Variablen besteht darin, dass die Initialisierung einer const-Variablen bis zur Laufzeit verzögert werden kann. Eine constexpr-Variable muss zum Zeitpunkt der Kompilierung initialisiert werden.  Alle constexpr-Variablen sind auch const.

- Eine Variable kann mit **constexpr**deklariert werden, wenn Sie einen Literaltyp aufweist und initialisiert wird. Wenn die Initialisierung von einem Konstruktor durchgeführt wird, muss der Konstruktor als **constexpr**deklariert werden.

- Ein Verweis kann als constexpr deklariert werden, wenn das Objekt, auf das er verweist, durch einen konstanten Ausdruck initialisiert wurde und alle impliziten Konvertierungen, die während der Initialisierung aufgerufen werden, auch konstante Ausdrücke sind.

- Alle Deklarationen einer **constexpr** -Variablen oder-Funktion müssen den **constexpr** -Spezifizierer aufweisen.

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="constexpr_functions"></a>constexpr-Funktionen

Eine **constexpr** -Funktion ist eine Funktion, deren Rückgabewert zur Kompilierzeit berechnet werden kann, wenn der Code benötigt wird. Die Verwendung von Code erfordert den Rückgabewert zum Zeitpunkt der Kompilierung, z. b. um eine **constexpr** -Variable zu initialisieren oder ein Nichttyp-Vorlagen Argument bereitzustellen. Wenn es sich bei den Argumenten um **constexpr** -Werte handelt, erzeugt eine **constexpr** -Funktion eine Kompilierzeit Konstante. Wenn Sie mit nicht-**constexpr** -Argumenten aufgerufen werden oder wenn der Wert zur Kompilierzeit nicht erforderlich ist, wird zur Laufzeit ein Wert erzeugt, wie eine reguläre Funktion. (Dieses duale Verhalten verhindert, dass Sie **constexpr** -und nicht-**constexpr** -Versionen derselben Funktion schreiben müssen.)

Eine **constexpr** -Funktion oder ein-Konstruktor ist implizit **Inline**.

Die folgenden Regeln gelten für constexpr-Funktionen:

- Eine **constexpr** -Funktion muss nur [Literaltypen](trivial-standard-layout-and-pod-types.md#literal_types)akzeptieren und zurückgeben.

- Eine **constexpr** -Funktion kann rekursiv sein.

- Er darf nicht [virtuell](../cpp/virtual-cpp.md)sein. Ein Konstruktor kann nicht als constexpr definiert werden, wenn die einschließende Klasse über virtuelle Basisklassen verfügt.

- Der Text kann als `= default` oder `= delete` definiert werden.

- Der Text kann keine **goto** -Anweisungen oder try-Blöcke enthalten.

- Eine explizite Spezialisierung einer nicht-constexpr-Vorlage kann als **constexpr**deklariert werden:

- Eine explizite Spezialisierung einer **constexpr** -Vorlage muss nicht gleichzeitig " **constexpr**" lauten:

Die folgenden Regeln gelten für **constexpr** -Funktionen in Visual Studio 2017 und höher:

- Sie kann **if** -und **Switch** -Anweisungen sowie alle Schleifen Anweisungen enthalten, einschließlich **für**, Bereichs basiert für, **while**und **do-while**.

- Sie kann lokale Variablen Deklarationen enthalten, aber die Variable muss initialisiert werden, muss ein Literaltyp sein und kann nicht statisch oder Thread lokal sein. Die lokal deklarierte Variable muss nicht konstant sein und mutieren.

- Es ist nicht erforderlich, dass eine nicht statische Element Funktion von constexpr implizit konstant ist.

```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> Beim Debuggen eines nicht optimierten Debugbuilds können Sie im Visual Studio-Debugger erkennen, ob eine **constexpr** -Funktion zur Kompilierzeit durch Einfügen eines halte Punkts ausgewertet wird. Wenn der Haltepunkt erreicht wird, wurde die Funktion zur Laufzeit aufgerufen.  Wenn dies nicht der Fall ist, wurde die Funktion zum Zeitpunkt der Kompilierung aufgerufen.

## <a name="extern-constexpr"></a>extern (constexpr)

Die [/Zc: externconstexpr](../build/reference/zc-externconstexpr.md) -Compileroption bewirkt, dass der Compiler [externe Verknüpfungen](../c-language/external-linkage.md) auf Variablen anwendet, die mit **extern constexpr**deklariert werden. In früheren Versionen von Visual Studio und standardmäßig oder wenn **/Zc: externconstexpr-** angegeben ist, wendet Visual Studio eine interne Verknüpfung auf **constexpr** -Variablen an, auch wenn das **extern** -Schlüsselwort verwendet wird. Die Option **/Zc: externconstexpr** ist ab Visual Studio 2017 Update 15,6 verfügbar und ist standardmäßig deaktiviert. Die/permissive--Option aktiviert **/Zc: externconstexpr**nicht.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt **constexpr** -Variablen,-Funktionen und einen benutzerdefinierten Typ. In der letzten Anweisung in "Main ()" ist die **constexpr** -Member-Funktion "GetValue ()" ein Lauf Zeit Aufruf, da der Wert zum Zeitpunkt der Kompilierung nicht bekannt sein muss.

```cpp
// constexpr.cpp
// Compile with: cl /EHsc /W4 constexpr.cpp
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

// Compile-time computation of array length
template<typename T, int N>
constexpr int length(const T(&)[N])
{
    return N;
}

// Recursive constexpr function
constexpr int fac(int n)
{
    return n == 1 ? 1 : n * fac(n - 1);
}

// User-defined type
class Foo
{
public:
    constexpr explicit Foo(int i) : _i(i) {}
    constexpr int GetValue() const
    {
        return _i;
    }
private:
    int _i;
};

int main()
{
    // foo is const:
    constexpr Foo foo(5);
    // foo = Foo(6); //Error!

    // Compile time:
    constexpr float x = exp(5, 3);
    constexpr float y { exp(2, 5) };
    constexpr int val = foo.GetValue();
    constexpr int f5 = fac(5);
    const int nums[] { 1, 2, 3, 4 };
    const int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };

    // Run time:
    cout << "The value of foo is " << foo.GetValue() << endl;
}
```

## <a name="requirements"></a>Anforderungen

Visual Studio 2015 oder höher.

## <a name="see-also"></a>Siehe auch

[Deklarationen und Definitionen](../cpp/declarations-and-definitions-cpp.md)\
[const](../cpp/const-cpp.md)
