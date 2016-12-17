---
title: "&lt;chrono&gt;"
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
  - "chrono/std::chrono::nanoseconds"
  - "chrono/std::chrono::minutes"
  - "chrono/std::chrono::seconds"
  - "<chrono>"
  - "chrono/std::chrono::hours"
  - "chrono/std::chrono::milliseconds"
  - "chrono/std::chrono::microseconds"
dev_langs: 
  - "C++"
ms.assetid: 844de749-f306-482e-89bc-6f53c99c8324
caps.latest.revision: 17
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# &lt;chrono&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Schließen Sie den Standardheader \<chrono\> zum Definieren von Klassen und Funktionen ein, die die Zeitdauer und Zeitangaben darstellen und bearbeiten.  
  
 **\(Visual Studio 2015:\)** Die Implementierung von `steady_clock` wurde geändert, um die C\+\+\-Standardanforderungen für Zuverlässigkeit und Monotonie zu erfüllen.  `steady_clock` basiert nun auf QueryPerformanceCounter\(\), und `high_resolution_clock` ist jetzt ein typedef\-Element für `steady_clock`.  Demzufolge ist `steady_clock::time_point` in Visual C\+\+ jetzt ein typedef\-Element für `chrono::time_point<steady_clock>`; dies ist jedoch nicht unbedingt bei anderen Implementierungen der Fall.  
  
## Syntax  
  
```cpp  
#include <chrono>  
```  
  
### Literale  
 Literale in den Header \<chrono\> sind Mitglieder des Inline\-Namespaces literals::chrono\_literals.  Weitere Informationen finden Sie unter [chrono\-Literale](../standard-library/chrono-literals.md).  
  
|||  
|-|-|  
|operator "" h\(unsigned long long Val\) operator "" h\(long double Val\)|Gibt an, dass der Wert Stunden darstellt.|  
|operator "" min\(unsigned long long Val\)  operator "" min\(long double Val\)|Gibt an, dass der Wert Minuten darstellt.|  
|operator "" s\(unsigned long long Val\)operator "" s\(long double Val\)|Gibt an, dass der Wert Sekunden darstellt.|  
|operator "" ms\(unsigned long long Val\)operator "" ms\(long double Val\)|Gibt an, dass der Wert Millisekunden darstellt.|  
|operator "" us\(unsigned long long Val\)operator "" us\(long double Val\)|Gibt an, dass der Wert Mikrosekunden darstellt.|  
|operator "" ns\(unsigned long long Val\)operator "" ns\(long double Val\)|Gibt an, dass der Wert Nanosekunden darstellt.|  
  
### Klassen  
  
|Name|Beschreibung|  
|----------|------------------|  
|[duration\-Klasse](../standard-library/duration-class.md)|Beschreibt einen Typ, der ein Zeitintervall enthält.|  
|[time\_point\-Klasse](../standard-library/time-point-class.md)|Beschreibt einen Typ, der einen bestimmten Zeitpunkt darstellt.|  
  
### Strukturen  
  
|Name|Beschreibung|  
|----------|------------------|  
|[common\_type\-Struktur](../standard-library/common-type-structure.md)|Beschreibt Spezialisierungen der Vorlagenklasse [common\_type](../standard-library/common-type-class.md) für Instanziierungen von `duration` und `time_point`.|  
|[duration\_values\-Struktur](../standard-library/duration-values-structure.md)|Stellt bestimmte Werte für den `duration`\-Vorlagenparameter `Rep` bereit.|  
|[steady\_clock\-Struktur](../standard-library/steady-clock-struct.md)|Stellt eine `steady` Uhr dar.|  
|[system\_clock\-Struktur](../standard-library/system-clock-structure.md)|Stellt einen auf der Echtzeituhr des Systems basierten *Uhrtyp* dar.|  
|[treat\_as\_floating\_point\-Struktur](../standard-library/treat-as-floating-point-structure.md)|Gibt an, ob ein Typ als Gleitkommatyp behandelt werden kann.|  
  
### Funktionen  
  
|Name|Beschreibung|  
|----------|------------------|  
|[duration\_cast\-Funktion](../Topic/duration_cast%20Function.md)|Wandelt einen `duration`\-Objekt in einen angegebenen Typ um.|  
|[time\_point\_cast\-Funktion](../Topic/time_point_cast%20Function.md)|Wandelt einen `time_point`\-Objekt in einen angegebenen Typ um.|  
  
### Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[operator\- Operator \(STL\)](../Topic/operator-%20Operator%20\(STL\)1.md)|Operator für die Subtraktion oder Negation von `duration`\- und `time_point`\-Objekten.|  
|[operator\!\= Operator \(STL\)](../Topic/operator!=%20Operator%20\(STL\).md)|Ungleichheitsoperator, der mit `duration`\- oder `time_point`\-Objekten verwendet wird.|  
|[Operatormodulo \(STL\)](../Topic/operator%20modulo%20\(STL\).md)|Operator für Modulo\-Vorgänge für `duration`\-Objekte.|  
|[operator\* Operator \(STL\)](../Topic/operator*%20Operator%20\(STL\).md)|Multiplikationsoperator für `duration`\-Objekte.|  
|[operator\/ Operator \(STL\)](../Topic/operator-%20Operator%20\(STL\)2.md)|Divisionsoperator für `duration`\-Objekte.|  
|[operator\+ Operator \(STL\)](../Topic/operator+%20Operator%20\(STL\).md)|Fügt `duration`\- und `time_point`\-Objekte hinzu.|  
|[operator\< Operator \(STL\)](../Topic/operator%3C%20Operator%20\(STL\).md)|Bestimmt, ob ein `duration`\- oder `time_point`\-Objekt kleiner als ein anderes `duration`\- oder `time_point`\-Objekt ist.|  
|[operator\<\= Operator \(STL\)](../Topic/operator%3C=%20Operator%20\(STL\).md)|Bestimmt, ob ein `duration`\- oder `time_point`\-Objekt kleiner als oder gleich einem anderen `duration`\- oder `time_point`\-Objekt ist.|  
|[operator\=\= Operator \(STL\)](../Topic/operator==%20Operator%20\(STL\).md)|Bestimmt, ob zwei `duration`\-Objekte Zeitintervalle mit derselben Länge darstellen, oder ob zwei `time_point`\-Objekte den gleichen Zeitpunkt darstellen.|  
|[operator\> Operator \(STL\)](../Topic/operator%3E%20Operator%20\(STL\).md)|Bestimmt, ob ein `duration`\- oder `time_point`\-Objekt größer als ein anderes `duration`\- oder `time_point`\-Objekt ist.|  
|[operator\>\= Operator \(STL\)](../Topic/operator%3E=%20Operator%20\(STL\).md)|Bestimmt, ob ein `duration`\- oder `time_point`\-Objekt größer als oder gleich einem anderen `duration`\- oder `time_point`\-Objekt ist.|  
  
### Vordefinierte duration\-Typen  
 Weitere Informationen zu Verhältnistypen, die in den folgenden typedefs\-Elementen verwendet werden, finden Sie unter [\<ratio\>](../standard-library/ratio.md).  
  
|TypeDef|Beschreibung|  
|-------------|------------------|  
|`typedef duration<long long, nano> nanoseconds;`|Synonym für einen `duration`\-Typ, der über einen Teilstrichpunkt von einer Nanosekunde verfügt.|  
|`typedef duration<long long, micro> microseconds;`|Synonym für einen `duration`\-Typ, der über einen Teilstrichpunkt von einer Mikrosekunde verfügt.|  
|`typedef duration<long long, milli> milliseconds;`|Synonym für einen `duration`\-Typ, der über einen Teilstrichpunkt von einer Millisekunde verfügt.|  
|`typedef duration<long long> seconds;`|Synonym für einen `duration`\-Typ, der über einen Teilstrichpunkt von einer Sekunde verfügt.|  
|`typedef duration<int, ratio<60> > minutes;`|Synonym für einen `duration`\-Typ, der über einen Teilstrichpunkt von einer Minute verfügt.|  
|`typedef duration<int, ratio<3600> > hours;`|Synonym für einen `duration`\-Typ, der über einen Teilstrichpunkt von einer Stunde verfügt.|  
  
### Literale  
 **\(C \+\+ 11\)** Der \<chrono\>\-Header definiert die folgenden [benutzerdefinierten Literale](../cpp/user-defined-literals-cpp.md), die Sie für mehr Komfort, Typsicherheit und Verwaltbarkeit des Codes verwenden können.  Diese Literale werden im `literals::chrono_literals`\-Inlinenamespace definiert und sind im Bereich enthalten, wenn std::chrono innerhalb des Bereichs liegt.  
  
|Literal|Beschreibung|  
|-------------|------------------|  
|chrono::hours operator "" h\(unsigned long long Val\)|Gibt die Stunden als Integralwert an.|  
|chrono::duration\<double, ratio\<3600\> \> operator "" h\(long double Val\)|Gibt die Stunden als Gleitkommawert an.|  
|chrono::minutes \(operator "" min\)\(unsigned long long Val\)|Gibt die Minuten als Integralwert an.|  
|chrono::duration\<double, ratio\<60\> \> \(operator "" min\)\( long double Val\)|Gibt die Minuten als Gleitkommawert an.|  
|chrono::seconds operator "" s\(unsigned long long Val\)|Gibt die Minuten als Integralwert an.|  
|chrono::duration\<double\> operator "" s\(long double Val\)|Gibt die Sekunden als Gleitkommawert an.|  
|chrono::milliseconds operator "" ms\(unsigned long long Val\)|Gibt die Millisekunden als Integralwert an.|  
|chrono::duration\<double, milli\> operator "" ms\(long double Val\)|Gibt die Millisekunden als Gleitkommawert an.|  
|chrono::microseconds operator "" us\(unsigned long long Val\)|Gibt die Mikrosekunden als Integralwert an.|  
|chrono::duration\<double, micro\> operator "" us\(long double Val\)|Gibt die Mikrosekunden als Gleitkommawert an.|  
|chrono::nanoseconds operator "" ns\(unsigned long long Val\)|Gibt die Nanosekunden als Integralwert an.|  
|chrono::duration\<double, nano\> operator "" ns\(long double Val\)|Gibt die Nanosekunden als Gleitkommawert an.|  
|||  
  
## Hinweise  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)