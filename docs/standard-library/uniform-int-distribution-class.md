---
title: "uniform_int_distribution-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tr1.uniform_int_distribution"
  - "random/std::tr1::uniform_int_distribution"
  - "uniform_int_distribution"
  - "tr1::uniform_int_distribution"
  - "std.tr1.uniform_int_distribution"
  - "std::tr1::uniform_int_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "uniform_int_distribution-Klasse"
ms.assetid: a1867dcd-3bd9-4787-afe3-4b62692c1d04
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# uniform_int_distribution-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Generiert eine einheitliche \(jeder Wert ist gleichermaßen wahrscheinlich\) Ganzzahlverteilung innerhalb eines Ausgabebereiches, der inklusive\-inklusive ist.  
  
## Syntax  
  
```  
template<class IntType = int> class uniform_int_distribution { public:     // types     typedef IntType result_type;     struct param_type;     // constructors and reset functions     explicit uniform_int_distribution(IntType a = 0, IntType b = numeric_limits<IntType>::max());     explicit uniform_int_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     result_type a() const;     result_type b() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### Parameter  
 `IntType`  
 Der Ganzzahlergebnistyp. Der Standardwert ist `int`.  Die möglichen Typen finden Sie unter [\<random\>](../standard-library/random.md).  
  
## Hinweise  
 Die Vorlagenklasse beschreibt eine inklusive\-inklusive Verteilung, die Werte eines vom Benutzer angegebenen Ganzzahltyps mit einer Verteilung erzeugt, damit jeder Wert gleichermaßen wahrscheinlich ist.  Die folgende Tabelle ist mit Artikeln über einzelne Member verknüpft.  
  
||||  
|-|-|-|  
|[uniform\_int\_distribution::uniform\_int\_distribution](../Topic/uniform_int_distribution::uniform_int_distribution.md)|`uniform_int_distribution::a`|`uniform_int_distribution::param`|  
|`uniform_int_distribution::operator()`|`uniform_int_distribution::b`|[uniform\_int\_distribution::param\_type](../Topic/uniform_int_distribution::param_type.md)|  
  
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
  
void test(const int a, const int b, const int s) {  
  
    // uncomment to use a non-deterministic seed  
    //    std::random_device rd;  
    //    std::mt19937 gen(rd());  
    std::mt19937 gen(1729);  
  
    std::uniform_int_distribution<> distr(a, b);  
  
    std::cout << "lower bound == " << distr.a() << std::endl;  
    std::cout << "upper bound == " << distr.b() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<int, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Distribution for " << s << " samples:" << std::endl;  
    for (const auto& elem : histogram) {  
        std::cout << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    int a_dist = 1;  
    int b_dist = 10;  
  
    int samples = 100;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter an integer value for the lower bound of the distribution: ";  
    std::cin >> a_dist;  
    std::cout << "Enter an integer value for the upper bound of the distribution: ";  
    std::cin >> b_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(a_dist, b_dist, samples);  
}  
  
```  
  
## Ausgabe  
  **Drücken Sie STRG\-Z, um die Dateneingabe zu umgehen und die Ausführung mit Standardwerten zu starten.  Geben Sie einen Ganzzahlwert für die untere Grenze der Verteilung ein: 0**  
**Geben Sie einen Ganzzahlwert für die obere Grenze der Verteilung ein: 12**  
**Geben Sie einen Ganzzahlwert für die Samplinganzahl ein: 200**  
**Untergrenze \=\= 0**  
**Obergrenze \=\= 12**  
**Verteilung für 200 Samplings:**  
 **0 :::::::::::::::**  
 **1 :::::::::::::::::::::**  
 **2 ::::::::::::::::::**  
 **3 :::::::::::::::**  
 **4 :::::::**  
 **5 :::::::::::::::::::::**  
 **6 :::::::::::::**  
 **7 ::::::::::**  
 **8 :::::::::::::::**  
 **9 :::::::::::::**  
 **10 ::::::::::::::::::::::**  
 **11 :::::::::::::**  
 **12 :::::::::::::::::**    
## Anforderungen  
 **Header:** \<random\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<random\>](../standard-library/random.md)