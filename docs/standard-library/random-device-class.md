---
title: "random_device-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "random_device"
  - "random/std::tr1::random_device"
  - "tr1.random_device"
  - "std::tr1::random_device"
  - "std.tr1.random_device"
  - "tr1::random_device"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "random_device-Klasse"
  - "random_device-Klasse [TR1]"
ms.assetid: 4393d515-0cb6-4e0d-a2ba-c780f05dc1bf
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# random_device-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Generiert eine zufällige Sequenz von einem externen Gerät.  
  
## Syntax  
  
```  
class random_device { public:     typedef unsigned int result_type;     // cosntructor     explicit random_device(const std::string& token = "");     // properties     static result_type min();     static result_type max();     double entropy() const;     // generate     result_type operator()();     // no-copy functions     random_device(const random_device&) = delete;     void operator=(const random_device&) = delete; };  
```  
  
## Mitglieder  
  
|||  
|-|-|  
|[random\_device::random\_device](../Topic/random_device::random_device.md)|[random\_device::entropy](../Topic/random_device::entropy.md)|  
|[random\_device::operator\(\)](../Topic/random_device::operator\(\).md)||  
  
## Hinweise  
 Die Klasse beschreibt eine Quelle von Zufallszahlen und darf \- aber muss nicht \- nach dem ISO C\+\+\-Standard nicht\-deterministisch oder kryptografisch sicher sein.  In der Visual Studio\-Implementierung sind die produzierten Werte nicht\-deterministisch und kryptografisch sicher, aber sie läuft langsamer als aus Modulen und Moduladaptern erstellte Generatoren \(wie [mersenne\_twister\_engine](../standard-library/mersenne-twister-engine-class.md), das hochwertige und schnelle Modul für die meisten Anwendungen\).  
  
 `random_device`\-Ergebnisse sind gleichförmig im geschlossenen Bereich \[`0, 2`<sup>32</sup>\) verteilt.  
  
 Es ist nicht garantiert, dass `random_device` zu einem nicht blockierenden Aufruf führt.  
  
 Im Allgemeinen wird `random_device` verwendet, um andere mithilfe von Modulen oder Moduladaptern erstellte Generatoren mit Startwerten auszustatten.  Weitere Informationen finden Sie unter [\<random\>](../standard-library/random.md).  
  
## Beispiel  
 Mit dem folgenden Code werden die grundlegende Funktion dieser Klasse und Beispielergebnisse veranschaulicht.  Aufgrund der nicht\-deterministischen Struktur von `random_device` entsprechen die im Abschnitt **Ausgabe** gezeigten Zufallswerte nicht Ihren Ergebnissen.  Dies ist normal und zu erwarten.  
  
```cpp  
// random_device_engine.cpp   
// cl.exe /W4 /nologo /EHsc /MTd   
#include <random>   
#include <iostream>   
using namespace std;  
  
int main()   
{   
    random_device gen;   
  
    cout << "entropy == " << gen.entropy() << endl;   
    cout << "min == " << gen.min() << endl;   
    cout << "max == " << gen.max() << endl;   
  
    cout << "a random value == " << gen() << endl;   
    cout << "a random value == " << gen() << endl;   
    cout << "a random value == " << gen() << endl;   
}  
```  
  
 **Ausgabe:**  
  
  **Entropie \=\= 32**  
**Min \=\= 0**  
**Max \=\= 4294967295**  
**10 Zufallswerte:**  
**4183829181**  
**1454391608**  
**1176278697**  
**2468830096**  
**3959347222**  
**1803123400**  
**1339590545**  
**1304896877**  
**604088490**  
**2293276253** Dieses Beispiel ist vereinfacht und nicht repräsentativ für den generellen Verwendungsfall dieses Generators.  Ein repräsentativeres Codebeispiel finden Sie unter [\<random\>](../standard-library/random.md).  
  
## Anforderungen  
 **Header:** \<random\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<random\>](../standard-library/random.md)