---
title: "geometric_distribution-Klasse"
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
  - "std.tr1.geometric_distribution"
  - "random/std::tr1::geometric_distribution"
  - "tr1::geometric_distribution"
  - "tr1.geometric_distribution"
  - "geometric_distribution"
  - "std::tr1::geometric_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "geometric_distribution-Klasse"
  - "geometric_distribution-Klasse [TR1]"
ms.assetid: 38f933af-3b49-492e-9d26-b6b272a60013
caps.latest.revision: 24
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# geometric_distribution-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Generiert eine geometrische Verteilung.  
  
## Syntax  
  
```  
template<class IntType = int> class geometric_distribution { public:     // types     typedef IntType result_type;     struct param_type;     // constructors and reset functions     explicit geometric_distribution(double p = 0.5);     explicit geometric_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     double p() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### Parameter  
 `IntType`  
 Der Ganzzahlergebnistyp. Der Standardwert ist `int`.  Die möglichen Typen finden Sie unter [\<random\>](../standard-library/random.md).  
  
## Hinweise  
 Diese Vorlagenklasse beschreibt eine Verteilung, die Werte eines benutzerdefinierten Ganzzahltyps mit einer geometrischen Verteilung produziert.  Die folgende Tabelle ist mit Artikeln über einzelne Member verknüpft.  
  
||||  
|-|-|-|  
|[geometric\_distribution::geometric\_distribution](../Topic/geometric_distribution::geometric_distribution.md)|`geometric_distribution::p`|`geometric_distribution::param`|  
|`geometric_distribution::operator()`||[geometric\_distribution::param\_type](../Topic/geometric_distribution::param_type.md)|  
  
 Die Eigenschaftsfunktion `p()` gibt den Wert für den gespeicherten Verteilungsparameter `p` zurück.  
  
 Weitere Informationen zu Verteilungsklassen und ihren Membern finden Sie unter [\<random\>](../standard-library/random.md).  
  
 Ausführliche Informationen über die Chi\-Quadrat\-Verteilung finden Sie im Wolfram MathWorld\-Artikel [Geometric Distribution](http://go.microsoft.com/fwlink/?LinkId=400529).  
  
## Beispiel  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double p, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
    std::mt19937 gen(1701);  
  
    std::geometric_distribution<> distr(p);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "p() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.p() << std::endl;  
  
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
    double p_dist = 0.5;  
  
    int samples = 100;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the \'p\' distribution parameter: ";  
    std::cin >> p_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(p_dist, samples);  
}  
  
```  
  
## Ausgabe  
 Erster Test:  
  
  **Drücken Sie STRG\-Z, um die Dateneingabe zu umgehen und die Ausführung mit Standardwerten zu starten.  Geben Sie einen Gleitkommawert für den Verteilungsparameter 'p' ein: 5**  
**Geben Sie einen Ganzzahlwert für die Samplinganzahl ein: 100**  
**min\(\) \=\= 0**  
**max\(\) \=\= 2147483647**  
**p\(\) \=\= 0.5000000000**  
**Verteilung für 100 Samplings:**  
 **0 ::::::::::::::::::::::::::::::::::::::::::::::::::::**  
 **1 ::::::::::::::::::::::::**  
 **2 ::::::::::::::**  
 **3 :::::**  
 **4 ::**  
 **5 ::**  
 **6 :**  Zweiter Test:  
  
  **Drücken Sie STRG\-Z, um die Dateneingabe zu umgehen und die Ausführung mit Standardwerten zu starten.  Geben Sie einen Gleitkommawert für den Verteilungsparameter 'p' ein: 1**  
**Geben Sie einen Ganzzahlwert für die Samplinganzahl ein: 100**  
**min\(\) \=\= 0**  
**max\(\) \=\= 2147483647**  
**p\(\) \=\= 0.1000000000**  
**Verteilung für 100 Samplings:**  
 **0 :::::::::**  
 **1 :::::::::::**  
 **2 :::::::**  
 **3 ::::::::**  
 **4 ::::::::**  
 **5 ::::::**  
 **6 :::::**  
 **7 ::::::**  
 **8 :::::**  
 **9 ::::**  
 **10 ::::**  
 **11 ::**  
 **12 :**  
 **13 :**  
 **14 :::**  
 **15 ::::**  
 **16 :::**  
 **17 :**  
 **18 :**  
 **19 :**  
 **20 ::**  
 **21 :**  
 **22 :**  
 **23 :**  
 **28 ::**  
 **33 :**  
 **35 :**  
 **40 :**    
## Anforderungen  
 **Header:** \<random\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<random\>](../standard-library/random.md)