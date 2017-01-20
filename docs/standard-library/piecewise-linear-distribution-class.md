---
title: "piecewise_linear_distribution-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "std::tr1::piecewise_linear_distribution"
  - "tr1.piecewise_linear_distribution"
  - "piecewise_linear_distribution"
  - "std.tr1.piecewise_linear_distribution"
  - "random/std::tr1::piecewise_linear_distribution"
  - "tr1::piecewise_linear_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "piecewise_linear_distribution-Klasse"
ms.assetid: cd141152-7163-4754-8f98-c6d6500005e0
caps.latest.revision: 21
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# piecewise_linear_distribution-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Generiert eine stückweise lineare Verteilung mit Intervallen von variierender Weite und in jedem Intervall linear variierender Wahrscheinlichkeit.  
  
## Syntax  
  
```  
template<class RealType = double>  
class piecewise_linear_distribution  
{  
public:  
    // types  
    typedef RealType result_type;  
    struct param_type;  
    // constructor and reset functions  
    piecewise_linear_distribution();  
    template<class InputIteratorI, class InputIteratorW>  
    piecewise_linear_distribution(InputIteratorI firstI, InputIteratorI lastI, InputIteratorW firstW);  
    template<class UnaryOperation>  
    piecewise_linear_distribution(initializer_list<RealType> intervals, UnaryOperation weightfunc);  
    template<class UnaryOperation>  
    piecewise_linear_distribution(size_t count, RealType xmin, RealType xmax, UnaryOperation weightfunc);  
    explicit piecewise_linear_distribution(const param_type& parm);  
    void reset();  
    // generating functions  
    template<class URNG>  
    result_type operator()(URNG& gen);  
    template<class URNG>  
    result_type operator()(URNG& gen, const param_type& parm);  
    // property functions  
    vector<result_type> intervals() const;  
    vector<result_type> densities() const;  
    param_type param() const;  
    void param(const param_type& parm);  
    result_type min() const;  
    result_type max() const;  
};  
```  
  
#### Parameter  
 `RealType`  
 Der Gleitkommaergebnistyp. Der Standardwert ist `double`. Mögliche Typen finden Sie unter [\<random\>](../standard-library/random.md).  
  
## Hinweise  
 Die Sampling\-Verteilung weist Intervalle von variierender Breite und in jedem Intervall linear variierender Wahrscheinlichkeit auf. Informationen über weitere Sampling\-Verteilungen erhalten Sie unter [piecewise\_constant\_distribution](../standard-library/piecewise-constant-distribution-class.md) und [discrete\_distribution](../standard-library/discrete-distribution-class.md)..  
  
 Die folgende Tabelle ist mit Artikeln über einzelne Member verknüpft:  
  
||||  
|-|-|-|  
|[piecewise\_linear\_distribution::piecewise\_linear\_distribution](../Topic/piecewise_linear_distribution::piecewise_linear_distribution.md)|`piecewise_linear_distribution::intervals`|`piecewise_linear_distribution::param`|  
|`piecewise_linear_distribution::operator()`|`piecewise_linear_distribution::densities`|[piecewise\_linear\_distribution::param\_type](../Topic/piecewise_linear_distribution::param_type.md)|  
  
 Die Eigenschaftsfunktion `intervals()` gibt einen `vector<RealType>` mit dem Satz gespeicherter Intervalle der Verteilung zurück.  
  
 Die Eigenschaftsfunktion `densities()` gibt einen `vector<RealType>` mit den für jeden Intervallsatz gespeicherten Dichten zurück, die entsprechend den in den Konstruktorparametern genannten Gewichten berechnet werden.  
  
 Weitere Informationen zur von verteilungsklassen und deren Member finden Sie unter [\<random\>](../standard-library/random.md).  
  
## Beispiel  
  
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
  
    // Three intervals, non-uniform: 0 to 1, 1 to 6, and 6 to 15  
    vector<double> intervals{ 0, 1, 6, 15 };  
    // weights determine the densities used by the distribution  
    vector<double> weights{ 1, 5, 5, 10 };  
  
    piecewise_linear_distribution<double> distr(intervals.begin(), intervals.end(), weights.begin());  
  
    cout << endl;  
    cout << "min() == " << distr.min() << endl;  
    cout << "max() == " << distr.max() << endl;  
    cout << "intervals (index: interval):" << endl;  
    vector<double> i = distr.intervals();  
    int counter = 0;  
    for (const auto& n : i) {  
        cout << fixed << setw(11) << counter << ": " << setw(14) << setprecision(10) << n << endl;  
        ++counter;  
    }  
    cout << endl;  
    cout << "densities (index: density):" << endl;  
    vector<double> d = distr.densities();  
    counter = 0;  
    for (const auto& n : d) {  
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
        cout << setw(5) << elem.first << '-' << elem.first + 1 << ' ' << string(elem.second, ':') << endl;  
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
  
## Ausgabe  
  
```Output  
Verwenden Sie STRG + Z, um die Dateneingabe zu umgehen und die Ausführung mit Standardwerten. Geben Sie einen Ganzzahlwert für die Samplinganzahl: 100min() == 0max() == 15intervals (Index: Intervall): 0: "0.0000000000" 1: 1.0000000000 2: 6.0000000000 3: 15.0000000000densities (Index: Dichte): 0: 0.0645161290 1: 0.3225806452 2: 0.3225806452 3: 0.6451612903Distribution für 100 Samplings: 0-1::: 1 und 2::: 2-3::: 3 und 4::: 4 und 5::: 5-6::: 6 und 7::: 7 bis 8::: 8 – 9::: 9 und 10::: 10-11::: 11-12::: 12 und 13::: 13-14::: 14 – 15:::  
```  
  
## Anforderungen  
 **Header:** \<random\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<random\>](../standard-library/random.md)