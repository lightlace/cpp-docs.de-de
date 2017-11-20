---
title: lognormal_distribution-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- random/std::lognormal_distribution
- random/std::lognormal_distribution::reset
- random/std::lognormal_distribution::m
- random/std::lognormal_distribution::s
- random/std::lognormal_distribution::param
- random/std::lognormal_distribution::min
- random/std::lognormal_distribution::max
- random/std::lognormal_distribution::operator()
- random/std::lognormal_distribution::param_type
- random/std::lognormal_distribution::param_type::m
- random/std::lognormal_distribution::param_type::s
- random/std::lognormal_distribution::param_type::operator==
- random/std::lognormal_distribution::param_type::operator!=
- random/std::lognormal_distribution::param_type
dev_langs:
- C++
helpviewer_keywords:
- std::lognormal_distribution [C++]
- std::lognormal_distribution [C++], reset
- std::lognormal_distribution [C++], m
- std::lognormal_distribution [C++], s
- std::lognormal_distribution [C++], param
- std::lognormal_distribution [C++], min
- std::lognormal_distribution [C++], max
- std::lognormal_distribution [C++], param_type
- std::lognormal_distribution [C++], param_type
ms.assetid: f2d6a431-6c3a-4370-b12e-4adb4ddf6cc4
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 60289557e00642bfd46cbbf2d23084d148307995
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="lognormaldistribution-class"></a>lognormal_distribution-Klasse
Generiert eine Lognormalverteilung.  
  
## <a name="syntax"></a>Syntax  
```  
template <class RealType = double>  
class lognormal_distribution  
   {  
public:  
   // types  
   typedef RealType result_type;  
   struct param_type;  
   // constructor and reset functions  
   explicit lognormal_distribution(result_type m = 0.0, result_type s = 1.0);
   explicit lognormal_distribution(const param_type& parm);
   void reset();
   // generating functions  
   template <class URNG>  
   result_type operator()(URNG& gen);
   template <class URNG>  
   result_type operator()(URNG& gen, const param_type& parm);
   // property functions  
   result_type m() const;
   result_type s() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };  
```  
### <a name="parameters"></a>Parameter  
*RealType*  
Der Gleitkommaergebnistyp. Der Standardwert ist `double`. Die möglichen Typen finden Sie unter [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Hinweise  
Die Vorlagenklasse beschreibt eine Verteilung, die Werte eines benutzerdefinierten ganzzahligen Typs produziert. Wenn kein entsprechend der Lognormalverteilung verteilter Wert ausgeben wird, geben Sie `double` ein. Die folgende Tabelle ist mit Artikeln über einzelne Member verknüpft.  
  
||||  
|-|-|-|  
|[lognormal_distribution](#lognormal_distribution)|`lognormal_distribution::m`|`lognormal_distribution::param`|  
|`lognormal_distribution::operator()`|`lognormal_distribution::s`|[param_type](#param_type)|  
  
Die Eigenschaftsfunktionen `m()` und `s()` geben die Werte für die gespeicherten Verteilungsparameter *m* bzw. *s* zurück.  
  
Das Eigenschaftsmember `param()` gibt das aktuell gespeicherte Verteilungspaket `param_type` zurück oder legt es fest.  

Die `min()`- und `max()`-Memberfunktion gibt das jeweils kleinst- und größtmögliche Ergebnis zurück.  
  
Die `reset()`-Memberfunktion verwirft alle zwischengespeicherten Werte, damit das Ergebnis des folgenden Aufrufs von `operator()` nicht von Werten abhängig ist, die vor dem Aufruf aus dem Modul bezogen wurden.  
  
Die `operator()`-Memberfunktionen geben den nächsten generierten Wert von entweder dem aktuellen oder dem spezifizierten Parameterpaket zurück, das auf dem URNG-Modul basiert.
  
Weitere Informationen zu Verteilungsklassen und ihren Membern finden Sie unter [\<random>](../standard-library/random.md).  
  
Ausführliche Informationen über die Lognormalverteilung finden Sie im Wolfram MathWorld-Artikel [LogNormal Distribution](http://go.microsoft.com/fwlink/LinkId=400917).  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
using namespace std;  
  
void test(const double m, const double s, const int samples) {  
  
    // uncomment to use a non-deterministic seed  
    //    random_device gen;  
    //    mt19937 gen(rd());  
    mt19937 gen(1701);  
  
    lognormal_distribution<> distr(m, s);  
  
    cout << endl;  
    cout << "min() == " << distr.min() << endl;  
    cout << "max() == " << distr.max() << endl;  
    cout << "m() == " << fixed << setw(11) << setprecision(10) << distr.m() << endl;  
    cout << "s() == " << fixed << setw(11) << setprecision(10) << distr.s() << endl;  
  
    // generate the distribution as a histogram  
    map<double, int> histogram;  
    for (int i = 0; i < samples; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    cout << "Distribution for " << samples << " samples:" << endl;  
    int counter = 0;  
    for (const auto& elem : histogram) {  
        cout << fixed << setw(11) << ++counter << ": "  
            << setw(14) << setprecision(10) << elem.first << endl;  
    }  
    cout << endl;  
}  
  
int main()  
{  
    double m_dist = 1;  
    double s_dist = 1;  
    int samples = 10;  
  
    cout << "Use CTRL-Z to bypass data entry and run using default values." << endl;  
    cout << "Enter a floating point value for the 'm' distribution parameter: ";  
    cin >> m_dist;  
    cout << "Enter a floating point value for the 's' distribution parameter (must be greater than zero): ";  
    cin >> s_dist;  
    cout << "Enter an integer value for the sample count: ";  
    cin >> samples;  
  
    test(m_dist, s_dist, samples);  
}  
```  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'm' distribution parameter: 0  
Enter a floating point value for the 's' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
 
min() == -1.79769e+308  
max() == 1.79769e+308  
m() == 0.0000000000  
s() == 1.0000000000  
Distribution for 10 samples:  
    1: 0.3862809339  
    2: 0.4128865601  
    3: 0.4490576787  
    4: 0.4862035428  
    5: 0.5930607126  
    6: 0.8190778771  
    7: 0.8902379317  
    8: 2.8332911667  
    9: 5.1359445565  
    10: 5.4406507912  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<random>  
  
 **Namespace:** std  
  
##  <a name="lognormal_distribution"></a> lognormal_distribution::lognormal_distribution  
 Erstellt die Verteilung.  
  
```  
explicit lognormal_distribution(RealType m = 0.0, RealType s = 1.0);
explicit lognormal_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>Parameter  
*m*  
Der `m`-Verteilungsparameter.  
  
*s*  
Der `s`-Verteilungsparameter.  
  
*parm*  
Die für die Erstellung der Verteilung verwendete `param_type`-Struktur.  
  
### <a name="remarks"></a>Hinweise  
**Vorbedingung:** `0.0 < s`  
  
Mit dem ersten Konstruktor wird ein Objekt erstellt, in dessen gespeichertem `m`-Wert der Wert *m* enthalten ist und dessen gespeicherter `s`-Wert den Wert *s* enthält.  
  
Mit dem zweiten Konstruktor wird ein Objekt erstellt, dessen gespeicherte Parameter von *parm* initialisiert werden. Sie können die aktuellen Parameter einer vorhandenen Verteilung abrufen und festlegen, indem Sie die Memberfunktion `param()` aufrufen.  
  
##  <a name="param_type"></a> lognormal_distribution::param_type  
Speichert die Parameter der Verteilung.  
  
```  
struct param_type {  
   typedef lognormal_distribution<result_type> distribution_type;  
   param_type(result_type m = 0.0, result_type s = 1.0);
   result_type m() const;
   result_type s() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
};  
```    
### <a name="parameters"></a>Parameter  
*m*  
Der `m`-Verteilungsparameter.  
  
*s*  
Der `s`-Verteilungsparameter.  
  
*right*  
Die `param_type`-Struktur, mit der verglichen wird.  
  
### <a name="remarks"></a>Hinweise  
**Vorbedingung:** `0.0 < s`  
  
Diese Struktur kann bei der Instanziierung an den Klassenkonstruktor des Verteilers, an die Memberfunktion `param()` (zur Festlegung der gespeicherten Parameter einer vorhandenen Verteilung) und an `operator()` (zur Verwendung anstelle der gespeicherten Parameter) übergeben werden.  
  
## <a name="see-also"></a>Siehe auch  
[\<random>](../standard-library/random.md)

