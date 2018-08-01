---
title: Zeitpunkt der Deklaration in C++ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- point of declaration
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89f94cdee6be18436b3f39f840fb7880e5860adb
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39409375"
---
# <a name="point-of-declaration-in-c"></a>Zeitpunkt der Deklaration in C++
Es wird angenommen, dass ein Name unmittelbar nach seinem Deklarator, jedoch vor seinem (optionalen) Initialisierer deklariert wird. (Weitere Informationen über Deklaratoren finden Sie unter [Deklarationen und Definitionen](declarations-and-definitions-cpp.md).)  
  
 Betrachten Sie das folgende Beispiel:  
  
```cpp 
// point_of_declaration1.cpp  
// compile with: /W1   
double dVar = 7.0;  
int main()  
{  
   double dVar = dVar;   // C4700  
}  
```  
  
 Wenn der Punkt der Deklaration *nach* die Initialisierung, und klicken Sie dann auf der lokalen `dVar` würde zu 7.0, den Wert der globalen Variablen initialisiert werden `dVar`. Da dies jedoch nicht der Fall ist, wird `dVar` mit einem nicht definierten Wert initialisiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Bereich](../cpp/scope-visual-cpp.md)