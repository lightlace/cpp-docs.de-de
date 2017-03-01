---
title: uniform_int_distribution-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- uniform_int_distribution
- std::uniform_int_distribution
- random/std::uniform_int_distribution
- std::uniform_int_distribution::reset
- random/std::uniform_int_distribution::reset
- std::uniform_int_distribution::a
- random/std::uniform_int_distribution::a
- std::uniform_int_distribution::b
- random/std::uniform_int_distribution::b
- std::uniform_int_distribution::param
- random/std::uniform_int_distribution::param
- std::uniform_int_distribution::min
- random/std::uniform_int_distribution::min
- std::uniform_int_distribution::max
- random/std::uniform_int_distribution::max
- std::uniform_int_distribution::operator()
- random/std::uniform_int_distribution::operator()
- std::uniform_int_distribution::param_type
- random/std::uniform_int_distribution::param_type
- std::uniform_int_distribution::param_type::a
- random/std::uniform_int_distribution::param_type::a
- std::uniform_int_distribution::param_type::b
- random/std::uniform_int_distribution::param_type::b
- std::uniform_int_distribution::param_type::operator==
- random/std::uniform_int_distribution::param_type::operator==
- std::uniform_int_distribution::param_type::operator!=
- random/std::uniform_int_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- uniform_int_distribution class
ms.assetid: a1867dcd-3bd9-4787-afe3-4b62692c1d04
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 56ce46ec6b19a0ac5068193d5e1d3dfb0c9b4ee9
ms.lasthandoff: 02/24/2017

---
# <a name="uniformintdistribution-class"></a>uniform_int_distribution-Klasse
Generiert eine einheitliche (jeder Wert ist gleichermaßen wahrscheinlich) Ganzzahlverteilung innerhalb eines Ausgabebereiches, der inklusive-inklusive ist.  
  
## <a name="syntax"></a>Syntax  
```  
template<class IntType = int>
   class uniform_int_distribution {
public:    
   // types 
   typedef IntType result_type;    
   struct param_type;    
   
   // constructors and reset functions 
   explicit uniform_int_distribution(
      result_type a = 0, result_type b = numeric_limits<result_type>::max());
   explicit uniform_int_distribution(const param_type& parm);
   void reset();

   // generating functions 
   template <class URNG>  
      result_type operator()(URNG& gen);
   template <class URNG>  
      result_type operator()(URNG& gen, const param_type& parm);

   // property functions 
   result_type a() const;
   result_type b() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
};  
```  
### <a name="parameters"></a>Parameter  
*IntType*  
Der Ganzzahlergebnistyp. Der Standardwert ist `int`. Die möglichen Typen finden Sie unter [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Hinweise  
Die Vorlagenklasse beschreibt eine inklusive-inklusive Verteilung, die Werte eines vom Benutzer angegebenen Ganzzahltyps mit einer Verteilung erzeugt, damit jeder Wert gleichermaßen wahrscheinlich ist. Die folgende Tabelle ist mit Artikeln über einzelne Member verknüpft.  
  
||||  
|-|-|-|  
|[uniform_int_distribution::uniform_int_distribution](#uniform_int_distribution__uniform_int_distribution)|`uniform_int_distribution::a`|`uniform_int_distribution::param`|  
|`uniform_int_distribution::operator()`|`uniform_int_distribution::b`|[uniform_int_distribution::param_type](#uniform_int_distribution__param_type)|  
  
Das Eigenschaftsmember `a()` gibt die aktuell gespeicherte Untergrenze der Verteilung zurück, während `b()` die aktuell gespeicherte Obergrenze zurückgibt. Für diese Verteilungsklasse sind diese Mindest- und Höchstwerte dieselben wie die von den allgemeinen Eigenschaftsfunktionen `min()` und `max()` zurückgegebenen.  
  
Das Eigenschaftsmember `param()` gibt das aktuell gespeicherte Verteilungspaket `param_type` zurück oder legt es fest.  

Die `min()`- und `max()`-Memberfunktion gibt das jeweils kleinst- und größtmögliche Ergebnis zurück.  
  
Die `reset()`-Memberfunktion verwirft alle zwischengespeicherten Werte, damit das Ergebnis des folgenden Aufrufs von `operator()` nicht von Werten abhängig ist, die vor dem Aufruf aus dem Modul bezogen wurden.  
  
Die `operator()`-Memberfunktionen geben den nächsten generierten Wert von entweder dem aktuellen oder dem spezifizierten Parameterpaket zurück, das auf dem URNG-Modul basiert.
  
Weitere Informationen zu Verteilungsklassen und ihren Membern finden Sie unter [\<random>](../standard-library/random.md).  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.
Enter an integer value for the lower bound of the distribution: 0
Enter an integer value for the upper bound of the distribution: 12
Enter an integer value for the sample count: 200
lower bound == 0
upper bound == 12
Distribution for 200 samples:
    0 :::::::::::::::
    1 :::::::::::::::::::::
    2 ::::::::::::::::::
    3 :::::::::::::::
    4 :::::::
    5 :::::::::::::::::::::
    6 :::::::::::::
    7 ::::::::::
    8 :::::::::::::::
    9 :::::::::::::
   10 ::::::::::::::::::::::
   11 :::::::::::::
   12 :::::::::::::::::
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<random>  
  
 **Namespace:** std  
  
##  <a name="a-nameuniformintdistributionuniformintdistributiona--uniformintdistributionuniformintdistribution"></a><a name="uniform_int_distribution__uniform_int_distribution"></a> uniform_int_distribution::uniform_int_distribution  
Erstellt die Verteilung.  
  
```  
explicit uniform_int_distribution(
   result_type a = 0, result_type b = std::numeric_limits<result_type>::max());
explicit uniform_int_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>Parameter  
*a*  
Die Untergrenze (einschließend) für Zufallswerte.  
  
*b*  
Die Obergrenze (ausschließend) für Zufallswerte.  
  
*parm*  
Die für die Erstellung der Verteilung verwendete `param_type`-Struktur.  
  
### <a name="remarks"></a>Hinweise  
**Vorbedingung:** `a ≤ b`  
  
Mit dem ersten Konstruktor wird ein Objekt erstellt, in dessen gespeichertem `a`-Wert der Wert *a* enthalten ist und dessen gespeicherter `b`-Wert den Wert *b* enthält.  
  
Mit dem zweiten Konstruktor wird ein Objekt erstellt, dessen gespeicherte Parameter von *parm* initialisiert werden. Sie können die aktuellen Parameter einer vorhandenen Verteilung abrufen und festlegen, indem Sie die Memberfunktion `param()` aufrufen.  
  
##  <a name="a-nameuniformintdistributionparamtypea--uniformintdistributionparamtype"></a><a name="uniform_int_distribution__param_type"></a> uniform_int_distribution::param_type  
 Speichert die Parameter der Verteilung.  
```cpp  
struct param_type {  
   typedef uniform_int_distribution<result_type> distribution_type;  
   param_type(
      result_type a = 0, result_type b = std::numeric_limits<result_type>::max());
   result_type a() const;
   result_type b() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```  

### <a name="parameters"></a>Parameter  
*a*  
Die Untergrenze (einschließend) für Zufallswerte.  
  
*b*  
Die Obergrenze (ausschließend) für Zufallswerte.  
  
*right*  
Das mit diesem `param_type`-Objekt zu vergleichende Objekt.  
  
### <a name="remarks"></a>Hinweise  
**Vorbedingung:** `a ≤ b`  
  
Diese Struktur kann bei der Instanziierung an den Klassenkonstruktor des Verteilers, an die Memberfunktion `param()` (zur Festlegung der gespeicherten Parameter einer vorhandenen Verteilung) und an `operator()` (zur Verwendung anstelle der gespeicherten Parameter) übergeben werden.  
  
## <a name="see-also"></a>Siehe auch  
 [\<random>](../standard-library/random.md)




