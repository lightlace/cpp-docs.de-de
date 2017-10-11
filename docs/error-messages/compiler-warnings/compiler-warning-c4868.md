---
title: Compiler-Warnung C4868 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 26031e1ac6f39d745a772e1becf3f817213a59d8
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4868"></a>Compiler-Warnung C4868
'file(line_number)' Compiler möglicherweise die Reihenfolge der Auswertung von links nach rechts in der Initialisiererliste nicht erzwungen.  
  
 Die Elemente einer Initialisiererliste sind in Reihenfolge von links nach rechts ausgewertet werden. Es gibt zwei Fälle, in dem der Compiler wird diese Reihenfolge garantiert: der erste ist, wenn einige Elemente der Objekte, die als Wert übergeben werden Das zweite ist beim Kompilieren mit `/clr` und einige Elemente der Felder von Objekten oder Array-Elemente. Wenn der Compiler nicht, links-nach-rechts-Bewertung garantieren kann gibt die Warnung C4868 aus.  
  
 Diese Warnung kann als Ergebnis Compilerkonformität generiert werden, die für Visual C++ 2015 Update 2 vorgenommen wurde. Code, der vor Visual C++ 2015 Update 2 kompiliert wird nun C4868 generiert.  
  
 Diese Warnung ist standardmäßig deaktiviert. Verwendung `/Wall` um diese Warnung zu aktivieren.  
  
 Zur Behebung des Problems zuerst überlegen Sie, ob links-nach-rechts-Evaluierung der Initialisierer Listenelemente erforderlich ist, z. B. bei Auswertung der Elemente Reihenfolge unabhängige Nebeneffekte entstehen. In vielen Fällen ist die Reihenfolge, die Auswertung Elemente, Observable keinen Einfluss.  
  
 Wenn die Reihenfolge der Auswertung links-nach-rechts-sein muss, überlegen Sie, ob es möglich ist, die Elemente stattdessen (const) Verweis zu übergeben. Eine Änderung, wie dies beseitigt die Warnung im folgenden Codebeispiel.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C4868 generiert.  
  
```  
// C4868.cpp  
// compile with: /c /Wall  
#include <cstdio>  
  
class HasCopyConstructor  
{  
public:  
    int x;  
  
    HasCopyConstructor(int x): x(x) {}  
  
    HasCopyConstructor(const HasCopyConstructor& h): x(h.x)  
    {  
        printf("Constructing %d\n", h.x);  
    }  
};  
  
class TripWarning4868  
{  
public:  
    // note that taking "HasCopyConstructor" parameters by-value will trigger copy-construction.  
    TripWarning4868(HasCopyConstructor a, HasCopyConstructor b) {}  
  
    // This variation will not trigger the warning:  
    // TripWarning4868(const HasCopyConstructor& a, const HasCopyConstructor& b) {}  
};  
  
int main()  
{  
    HasCopyConstructor a{1};  
    HasCopyConstructor b{2};  
  
    // the warning will indicate the below line, the usage of the braced initializer list.  
    TripWarning4868 warningOnThisLine{a, b};  
};  
```
