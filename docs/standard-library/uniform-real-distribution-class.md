---
title: "uniform_real_distribution-Klasse"
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
  - "tr1::uniform_real_distribution"
  - "std::tr1::uniform_real_distribution"
  - "random/std::tr1::uniform_real_distribution"
  - "uniform_real_distribution"
  - "std.tr1.uniform_real_distribution"
  - "tr1.uniform_real_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "uniform_real_distribution-Klasse"
ms.assetid: 5cf906fd-0319-4984-b21b-98425cd7532d
caps.latest.revision: 18
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# uniform_real_distribution-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Generiert eine einheitliche \(jeder Wert ist gleichermaßen wahrscheinlich\) Gleitkommaverteilung innerhalb eines Ausgabebereichs, der inklusive\-exklusive ist.  
  
## Syntax  
  
```  
template<class RealType = double> class uniform_real_distribution { public:     // types     typedef RealType result_type;     struct param_type;     // constructors and reset functions     explicit uniform_real_distribution(RealType a = 0.0, RealType b = 1.0);     explicit uniform_real_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     result_type a() const;     result_type b() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### Parameter  
 `RealType`  
 Der Gleitkommaergebnistyp. Der Standardwert ist `double`.  Die möglichen Typen finden Sie unter [\<random\>](../standard-library/random.md).  
  
## Hinweise  
 Die Vorlagenklasse beschreibt eine inklusive\-exklusive Verteilung, die Werte eines vom Benutzer angegebenen Ganzzahltyps mit einer Verteilung erzeugt, damit jeder Wert gleichermaßen wahrscheinlich ist.  Die folgende Tabelle ist mit Artikeln über einzelne Member verknüpft.  
  
||||  
|-|-|-|  
|[uniform\_real\_distribution::uniform\_real\_distribution](../Topic/uniform_real_distribution::uniform_real_distribution.md)|`uniform_real_distribution::a`|`uniform_real_distribution::param`|  
|`uniform_real_distribution::operator()`|`uniform_real_distribution::b`|[uniform\_real\_distribution::param\_type](../Topic/uniform_real_distribution::param_type.md)|  
  
 Das Eigenschaftsmember `a()` gibt die aktuell gespeicherte Untergrenze der Verteilung zurück, während `b()` die aktuell gespeicherte Obergrenze zurückgibt.  Für diese Verteilungsklasse sind diese Höchst\- und Mindestwerte dieselben wie die von den allgemeinen Eigenschaftsfunktionen `min()` und `max()` zurückgegebenen \(beschrieben im Thema [\<random\>](../standard-library/random.md)\).  
  
 Weitere Informationen zu Verteilungsklassen und ihren Membern finden Sie unter [\<random\>](../standard-library/random.md).  
  
## Beispiel  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double a, const double b, const int s) {  
  
    // uncomment to use a non-deterministic seed  
    //    std::random_device rd;  
    //    std::mt19937 gen(rd());  
    std::mt19937 gen(1729);  
  
    std::uniform_real_distribution<> distr(a,b);  
  
    std::cout << "lower bound == " << distr.a() << std::endl;  
    std::cout << "upper bound == " << distr.b() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<double, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Distribution for " << s << " samples:" << std::endl;  
    int counter = 0;  
    for (const auto& elem : histogram) {  
        std::cout << std::fixed << std::setw(11) << ++counter << ": "   
            << std::setprecision(10) << elem.first << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double a_dist = 1.0;  
    double b_dist = 1.5;  
  
    int samples = 10;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the lower bound of the distribution: ";  
    std::cin >> a_dist;  
    std::cout << "Enter a floating point value for the upper bound of the distribution: ";  
    std::cin >> b_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(a_dist, b_dist, samples);  
}  
  
```  
  
## Ausgabe  
  **Drücken Sie STRG\-Z, um die Dateneingabe zu umgehen und die Ausführung mit Standardwerten zu starten.  Geben Sie einen Gleitkommawert für die Untergrenze der Verteilung ein: 0,5**  
**Geben Sie einen Gleitkommawert für die Obergrenze der Verteilung ein: 1**  
**Geben Sie einen Ganzzahlwert für die Samplinganzahl ein: 20**  
**Untergrenze \=\= 0,5**  
**Obergrenze \=\= 1**  
**Verteilung für 20 Samplings:**  
 **1: 0.5144304741**  
 **2: 0.6003997192**  
 **3: 0.6060792968**  
 **4: 0.6270416650**  
 **5: 0.6295091197**  
 **6: 0.6437749373**  
 **7: 0.6513740058**  
 **8: 0.7062379346**  
 **9: 0.7117609406**  
 **10: 0.7206888566**  
 **11: 0.7423223702**  
 **12: 0.7826033033**  
 **13: 0.8112872958**  
 **14: 0.8440467608**  
 **15: 0.8461254641**  
 **16: 0.8598305065**  
 **17: 0.8640874069**  
 **18: 0.8770968361**  
 **19: 0.9397858282**  
 **20: 0.9804645012**    
## Anforderungen  
 **Header:** \<random\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<random\>](../standard-library/random.md)