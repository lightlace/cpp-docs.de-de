---
title: Zeitpunkt der Deklaration in C++ | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- point of declaration
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 77f66182052cc2a031b7f1f8db8018f49b36801d
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="point-of-declaration-in-c"></a>Zeitpunkt der Deklaration in C++
Es wird angenommen, dass ein Name unmittelbar nach seinem Deklarator, jedoch vor seinem (optionalen) Initialisierer deklariert wird. (Weitere Informationen über Deklaratoren finden Sie unter [Deklarationen und Definitionen](declarations-and-definitions-cpp.md).)  
  
 Betrachten Sie das folgende Beispiel:  
  
```  
// point_of_declaration1.cpp  
// compile with: /W1   
double dVar = 7.0;  
int main()  
{  
   double dVar = dVar;   // C4700  
}  
```  
  
 Wäre der Zeitpunkt der Deklaration *nach* die Initialisierung, und klicken Sie dann auf der lokalen `dVar` würde werden auf 7,0 initialisiert, den Wert der globalen Variablen `dVar`. Da dies jedoch nicht der Fall ist, wird `dVar` mit einem nicht definierten Wert initialisiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Bereich](../cpp/scope-visual-cpp.md)
