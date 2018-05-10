---
title: discrete_distribution-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::discrete_distribution
- random/std::discrete_distribution::reset
- random/std::discrete_distribution::probabilities
- random/std::discrete_distribution::param
- random/std::discrete_distribution::min
- random/std::discrete_distribution::max
- random/std::discrete_distribution::operator()
- random/std::discrete_distribution::param_type
- random/std::discrete_distribution::param_type::probabilities
- random/std::discrete_distribution::param_type::operator==
- random/std::discrete_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- std::discrete_distribution [C++]
- std::discrete_distribution [C++], reset
- std::discrete_distribution [C++], probabilities
- std::discrete_distribution [C++], param
- std::discrete_distribution [C++], min
- std::discrete_distribution [C++], max
- std::discrete_distribution [C++], param_type
- std::discrete_distribution [C++], param_type
ms.assetid: 8c8ba8f8-c06f-4f07-b354-f53950142fcf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af8f5c543847c91903c9cb4ddf2502c0cc59dfa0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="discretedistribution-class"></a>discrete_distribution-Klasse

Generiert eine diskrete Ganzzahlverteilung mit Intervallen von gleicher Breite und in jedem Intervall eindeutiger Wahrscheinlichkeit.

## <a name="syntax"></a>Syntax

```cpp
template<class IntType = int>
class discrete_distribution
   {
public:
   // types
   typedef IntType result_type;
   struct param_type;

   // constructor and reset functions
   discrete_distribution();
   template <class InputIterator>
   discrete_distribution(InputIterator firstW, InputIterator lastW);
   discrete_distribution(initializer_list<double> weightlist);
   template <class UnaryOperation>
   discrete_distribution(size_t count, double xmin, double xmax, UnaryOperation funcweight);
   explicit discrete_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
   result_type operator()(URNG& gen);
   template <class URNG>
   result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   vector<double> probabilities() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };
```

### <a name="parameters"></a>Parameter

*IntType* der Integer-Ergebnistyp standardmäßig `int`. Mögliche Typen finden Sie unter [\<random>](../standard-library/random.md).

## <a name="remarks"></a>Hinweise

Die Sampling-Verteilung weist Intervalle von gleicher Breite und in jedem Intervall eindeutiger Wahrscheinlichkeit auf. Informationen zu weiteren Sampling-Verteilungen finden Sie unter [piecewise_linear_distribution Class (piecewise_linear_distribution-Klasse)](../standard-library/piecewise-linear-distribution-class.md) und [piecewise_constant_distribution Class (piecewise_constant_distribution-Klasse)](../standard-library/piecewise-constant-distribution-class.md).

Die folgende Tabelle ist mit Artikeln über einzelne Member verknüpft:

|||
|-|-|
|[discrete_distribution](#discrete_distribution)|`discrete_distribution::param`|
|`discrete_distribution::operator()`|[param_type](#param_type)|

Die Eigenschaftsfunktion `vector<double> probabilities()` gibt die einzelnen Eigenschaften für jede generierte Ganzzahl zurück.

Weitere Informationen zu Verteilungsklassen und ihren Membern finden Sie unter [\<random>](../standard-library/random.md).

## <a name="example"></a>Beispiel

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

using namespace std;

void test(const int s) {

    // uncomment to use a non-deterministic generator
    // random_device rd;
    // mt19937 gen(rd());
    mt19937 gen(1701);

    discrete_distribution<> distr({ 1, 2, 3, 4, 5 });

    cout << endl;
    cout << "min() == " << distr.min() << endl;
    cout << "max() == " << distr.max() << endl;
    cout << "probabilities (value: probability):" << endl;
    vector<double> p = distr.probabilities();
    int counter = 0;
    for (const auto& n : p) {
        cout << fixed << setw(11) << counter << ": " << setw(14) << setprecision(10) << n << endl;
        ++counter;
    }
    cout << endl;

    // generate the distribution as a histogram
    map<int, int> histogram;
    for (int i = 0; i < s; ++i) {
        ++histogram[distr(gen)];
    }

    // print results
    cout << "Distribution for " << s << " samples:" << endl;
    for (const auto& elem : histogram) {
        cout << setw(5) << elem.first << ' ' << string(elem.second, ':') << endl;
    }
    cout << endl;
}

int main()
{
    int samples = 100;

    cout << "Use CTRL-Z to bypass data entry and run using default values." << endl;
    cout << "Enter an integer value for the sample count: ";
    cin >> samples;

    test(samples);
}
```

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter an integer value for the sample count: 100
min() == 0
max() == 4
probabilities (value: probability):
          0:   0.0666666667
          1:   0.1333333333
          2:   0.2000000000
          3:   0.2666666667
          4:   0.3333333333

Distribution for 100 samples:
    0 :::
    1 ::::::::::::::
    2 ::::::::::::::::::
    3 :::::::::::::::::::::::::::::
    4 ::::::::::::::::::::::::::::::::::::
```

## <a name="requirements"></a>Anforderungen

**Header:** \<random>

**Namespace:** std

## <a name="discrete_distribution"></a> discrete_distribution::discrete_distribution

Erstellt die Verteilung.

```cpp
// default constructor
discrete_distribution();

// construct using a range of weights, [firstW, lastW)
template <class InputIterator>
discrete_distribution(InputIterator firstW, InputIterator lastW);

// construct using an initializer list for range of weights
discrete_distribution(initializer_list<double> weightlist);

// construct using unary operation function
template <class UnaryOperation>
discrete_distribution(size_t count, double low, double high, UnaryOperation weightfunc);

// construct from an existing param_type structure
explicit discrete_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parameter

*FirstW* der erste Iterator in der Liste aus der die Verteilung konstruiert.

*LastW* der letzte Iterator in der Liste aus der konstruiert der Verteilungs (nicht inklusiv, da Iteratoren für das Ende ein leeres Element verwenden).

*Weightlist* der [Initializer_list](../cpp/initializers.md) aus der die Verteilung konstruiert.

*Anzahl* die Anzahl von Elementen im Verteilungsbereich. Wenn `count==0` ist, äquivalent zum Standardkonstruktor (generiert immer Null).

*niedrige* den niedrigsten Wert im Verteilungsbereich.

*hohe* der höchste Wert im Verteilungsbereich.

*Weightfunc* das Objekt, das die Wahrscheinlichkeitsfunktion für die Verteilung darstellt. Sowohl der Parameter als auch der Rückgabewert müssen in `double` konvertierbar sein.

*Parm* der `param_type` Struktur für die Verteilung verwendete Parameterstruktur.

### <a name="remarks"></a>Hinweise

Der Standardkonstruktor erstellt ein Objekt, dessen gespeicherter Wahrscheinlichkeitswert ein Element mit dem Wert 1 aufweist. Dies führt zu einer Verteilung, die immer Null generiert.

Der Iteratorbereichskonstruktor mit den Parametern *firstW* und *lastW* erstellt mithilfe von Gewichtungswerten, die den Iteratoren während der Intervallsequenz [*firstW*, *lastW*] entnommen werden, ein Verteilungsobjekt.

Der Initialisiererlistenkonstruktor mit einem *weightlist*-Parameter erstellt ein Verteilungsobjekt mit Gewichtungen aus der Initialisiererliste *weightlist*.

Der Konstruktor mit den Parametern *count*, *low*, *high* und *weightfunc* erstellt ein Verteilungsobjekt, das anhand der folgenden Regeln initialisiert wird:

- Wenn *count* < 1, **n** = 1, und gleich dem Standardkonstruktor, der immer Null generiert.
- Wenn *count* > 0, **n** = *count*. Bereitgestellte **d** = (*hohe* - *niedrig*) / **n** ist größer als 0 (null), mit **d** uniform Unterbereiche, jedes Gewicht wie folgt zugewiesen: `weight[k] = weightfunc(x)`, wobei **x** = *niedrig* + **k**  *  **d** + **d** / 2, für **k** = 0,..., **n** - 1.

Der Konstruktor mit einem `param_type`-Parameter *parm* erstellt ein Verteilungsobjekt und verwendet dabei *parm* als gespeicherte Parameterstruktur.

## <a name="param_type"></a> discrete_distribution::param_type

Speichert alle Parameter der Verteilung.

```cpp
struct param_type {
   typedef discrete_distribution<result_type> distribution_type;
   param_type();

   // construct using a range of weights, [firstW, lastW)
   template <class InputIterator>
   param_type(InputIterator firstW, InputIterator lastW);

   // construct using an initializer list for range of weights
   param_type(initializer_list<double> weightlist);

   // construct using unary operation function
   template <class UnaryOperation>
   param_type(size_t count, double low, double high, UnaryOperation weightfunc);

   std::vector<double> probabilities() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>Parameter

*FirstW* der erste Iterator in der Liste aus der die Verteilung konstruiert.

*LastW* der letzte Iterator in der Liste aus der konstruiert der Verteilungs (nicht inklusiv, da Iteratoren für das Ende ein leeres Element verwenden).

*Weightlist* der [Initializer_list](../cpp/initializers.md) aus der die Verteilung konstruiert.

*Anzahl* die Anzahl von Elementen im Verteilungsbereich. Wenn *count* 0 ist, entspricht dies dem Standardkonstruktor (generiert immer Null).

*niedrige* den niedrigsten Wert im Verteilungsbereich.

*hohe* der höchste Wert im Verteilungsbereich.

*Weightfunc* das Objekt, das die Wahrscheinlichkeitsfunktion für die Verteilung darstellt. Sowohl der Parameter als auch der Rückgabewert müssen in `double` konvertierbar sein.

*Rechte* der `param_type` zu vergleichende Objekt.

### <a name="remarks"></a>Hinweise

Dieses Parameterpaket kann an `operator()` übergeben werden, um den Rückgabewert zu generieren.

## <a name="see-also"></a>Siehe auch

[\<random>](../standard-library/random.md)<br/>
