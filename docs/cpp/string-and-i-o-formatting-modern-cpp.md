---
title: Zeichenfolgen- und e-A-Formatierung (Modern C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 391648d71fa3d38a0f704a014c163b7f8b102e40
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32422383"
---
# <a name="string-and-io-formatting-modern-c"></a>Formatieren von Zeichenfolgen und Ein-/Ausgaben (Modern C++)
C++ [Iostreams](../standard-library/iostream.md) formatierter zeichenfolgenein-genutzt werden. Im folgenden Code wird das Festlegen von "cout" zum Formatieren einer ganzen Zahl für eine Hexadezimalausgabe dargestellt. Erst wird der aktuelle Zustand gespeichert, danach erfolgt das Zurücksetzen, da die Methode nach Übergabe der Zustandsformatierung an "cout" in dem Zustand verbleibt, bis sie geändert wird und nicht nur für eine Codezeile.  
  
```cpp  
#include <iostream>  
#include <iomanip>  
  
using namespace std;  
  
int main()   
{  
    ios state(nullptr);  
  
    cout << "The answer in decimal is: " << 42 << endl;  
  
    state.copyfmt(cout); // save current formatting  
    cout << "In hex: 0x" // now load up a bunch of formatting modifiers  
        << hex   
        << uppercase   
        << setw(8)   
        << setfill('0')   
        << 42            // the actual value we wanted to print out  
        << endl;  
    cout.copyfmt(state); // restore previous formatting  
}  
  
```  
  
 Dies kann vielen Fällen außerordentlich lästig sein. Alternativ können Sie "Boost.Format" aus den C++-Bibliotheken von Boost verwenden, obwohl das nicht dem Standard entspricht. Sie können alle Boost-Bibliothek Herunterladen der [Prioritätserhöhung](http://www.boost.org/) Website.  
  
 Einige Vorteile von "Boost.Format" sind:  
  
-   Sicher: Typsicher und löst eine Ausnahme bei Fehlern aus, z. B. bei der Angabe von zu wenigen oder zu vielen Elementen  
  
-   Erweiterbar: Funktioniert für jeden Typ, der gestreamt werden kann  
  
-   Bequem: Standard-Posix und ähnliche Formatzeichenfolgen  
  
 Obwohl "boost.Format" auf C++ basiert [Iostreams](../standard-library/iostream-programming.md), die sicher und erweiterbar sind, sie sind nicht leistungsoptimiert. Wenn Sie zur Optimierung der Leistung benötigen, sollten Sie C [Printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) und [Sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md), wobei es sich schnell und einfach zu verwenden. Allerdings sind sie nicht erweiterbar und können Sicherheitsrisiken bergen. (Sichere Versionen sind vorhanden, doch verursachen diese geringfügige Leistungseinbußen. Weitere Informationen finden Sie unter [Printf_s _printf_s_l, Wprintf_s _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) und [Sprintf_s, _sprintf_s_l, Swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)).  
  
 Im folgenden Code werden einige der Boost-Formatierungsfunktionen verdeutlicht.  
  
```cpp  
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );  
    // s contains "hello hello world"    
  
    for( auto i = 0; i < names.size(); ++i )  
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];  
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789  
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)   
 [\<Iostream >](../standard-library/iostream.md)   
 [\<Grenzen >](../standard-library/limits.md)   
 [\<iomanip>](../standard-library/iomanip.md)
