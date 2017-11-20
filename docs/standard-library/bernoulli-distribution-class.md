---
title: bernoulli_distribution-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- random/std::bernoulli_distribution
- random/std::bernoulli_distribution::reset
- random/std::bernoulli_distribution::p
- random/std::bernoulli_distribution::param
- random/std::bernoulli_distribution::min
- random/std::bernoulli_distribution::max
- random/std::bernoulli_distribution::operator()
- random/std::bernoulli_distribution::param_type
- random/std::bernoulli_distribution::param_type::p
- random/std::bernoulli_distribution::param_type::operator==
- random/std::bernoulli_distribution::param_type::operator!=
- random/std::bernoulli_distribution::param_type
dev_langs:
- C++
helpviewer_keywords:
- std::bernoulli_distribution [C++]
- std::bernoulli_distribution [C++], reset
- std::bernoulli_distribution [C++], p
- std::bernoulli_distribution [C++], param
- std::bernoulli_distribution [C++], min
- std::bernoulli_distribution [C++], max
- std::bernoulli_distribution [C++], param_type
- std::bernoulli_distribution [C++], param_type
ms.assetid: 586bcde1-95ca-411a-bf17-4aaf19482f34
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: e66f7d0cc0385fea47a9d023f9cb67170de48cb4
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="bernoullidistribution-class"></a>bernoulli_distribution-Klasse
Generiert eine Bernoulli-Verteilung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class bernoulli_distribution  
   {  
public:  
   // types  
   typedef bool result_type;  
   struct param_type;  

   // constructors and reset functions  
   explicit bernoulli_distribution(double p = 0.5);
   explicit bernoulli_distribution(const param_type& parm);
   void reset();
   
   // generating functions  
   template <class URNG>  
   result_type operator()(URNG& gen);
   template <class URNG>  
   result_type operator()(URNG& gen, const param_type& parm);
   
   // property functions  
   double p() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };  
```
  
### <a name="parameters"></a>Parameter  
  
*URNG* Das einheitliche Zufallszahlengenerator-Modul. Die möglichen Typen finden Sie unter [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Hinweise  
Die Klasse beschreibt eine Verteilung, die Werte vom Typ `bool` produziert. Diese werden entsprechend der diskreten Wahrscheinlichkeitsfunktion zur Bernoulli-Verteilung verteilt. Die folgende Tabelle ist mit Artikeln über einzelne Member verknüpft.  
  
||||  
|-|-|-|  
|[bernoulli_distribution](#bernoulli_distribution)|`bernoulli_distribution::p`|`bernoulli_distribution::param`|  
|`bernoulli_distribution::operator()`||[param_type](#param_type)|  
  
Das Eigenschaftsmember `p()` gibt den aktuell gespeicherten Verteilungsparameterwert `p` zurück.  
  
Der Eigenschaftenmember `param()` legt das gespeicherte Verteilungsparameterpaket `param_type` fest oder gibt es zurück.  

Die `min()`- und `max()`-Memberfunktion gibt das jeweils kleinst- und größtmögliche Ergebnis zurück.  
  
Die `reset()`-Memberfunktion verwirft alle zwischengespeicherten Werte, damit das Ergebnis des folgenden Aufrufs von `operator()` nicht von Werten abhängig ist, die vor dem Aufruf aus dem Modul bezogen wurden.  
  
Die `operator()`-Memberfunktionen geben den nächsten generierten Wert von entweder dem aktuellen oder dem spezifizierten Parameterpaket zurück, das auf dem URNG-Modul basiert.
  
Weitere Informationen zu Verteilungsklassen und ihren Membern finden Sie unter [\<random>](../standard-library/random.md).  
  
Ausführliche Informationen über die diskrete Wahrscheinlichkeitsfunktion zur Bernoulli-Verteilung finden Sie im Wolfram MathWorld-Artikel [Bernoulli Distribution](http://go.microsoft.com/fwlink/LinkId=398467).  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double p, const int s) {  
  
    // uncomment to use a non-deterministic seed  
    //    std::random_device rd;  
    //    std::mt19937 gen(rd());  
    std::mt19937 gen(1729);  
  
    std::bernoulli_distribution distr(p);  
  
    std::cout << "p == " << distr.p() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<bool, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Histogram for " << s << " samples:" << std::endl;  
    for (const auto& elem : histogram) {  
        std::cout << std::boolalpha << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double p_dist = 0.5;  
    int samples = 100;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a double value for p distribution (where 0.0 <= p <= 1.0): ";  
    std::cin >> p_dist;  
    std::cout << "Enter an integer value for a sample count: ";  
    std::cin >> samples;  
  
    test(p_dist, samples);  
}  
```  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .45  
Enter an integer value for a sample count: 100  
p == 0.45  
Histogram for 100 samples:  
false :::::::::::::::::::::::::::::::::::::::::::::::::::::::::::
 true :::::::::::::::::::::::::::::::::::::::::
```  
  
## <a name="requirements"></a>Anforderungen  
**Header:** \<random>  
  
**Namespace:** std  
  
##  <a name="bernoulli_distribution"></a> bernoulli_distribution::bernoulli_distribution  
Erstellt die Verteilung.  
  
```  
explicit bernoulli_distribution(double p = 0.5);
explicit bernoulli_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>Parameter  
*p*  
 Der gespeicherte `p`-Verteilungsparameter.  
  
*parm*  
 Die für die Erstellung der Verteilung verwendete `param_type`-Struktur.  
  
### <a name="remarks"></a>Hinweise  
 **Vorbedingung:** `0.0 ≤ p ≤ 1.0`  
  
Der erste Konstruktor konstruiert ein Objekt, dessen gespeicherter `p`-Wert den Wert *p* enthält.  
  
Mit dem zweiten Konstruktor wird ein Objekt erstellt, dessen gespeicherte Parameter von *parm* initialisiert werden. Sie können die aktuellen Parameter einer vorhandenen Verteilung abrufen und festlegen, indem Sie die Memberfunktion `param()` aufrufen.  
  
##  <a name="param_type"></a> bernoulli_distribution::param_type  
Enthält die Parameter der Verteilung.  
  
struct param_type {  
   typedef bernoulli_distribution distribution_type;  
   param_type(double p = 0.5); double p() const;

   bool operator==(const param_type& right) const; bool operator!=(const param_type& right) const; };  
  
### <a name="parameters"></a>Parameter  
*p*  
Der gespeicherte `p`-Verteilungsparameter.  
  
### <a name="remarks"></a>Hinweise  
**Vorbedingung:** `0.0 ≤ p ≤ 1.0`  
  
Diese Struktur kann bei der Instanziierung an den Klassenkonstruktor des Verteilers, an die Memberfunktion `param()` (zur Festlegung der gespeicherten Parameter einer vorhandenen Verteilung) und an `operator()` (zur Verwendung anstelle der gespeicherten Parameter) übergeben werden.  
  
## <a name="see-also"></a>Siehe auch  
 [\<random>](../standard-library/random.md)


