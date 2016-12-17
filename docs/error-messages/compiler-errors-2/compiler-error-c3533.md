---
title: "Compilerfehler C3533"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C3533"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3533"
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3533
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typ": ein Parameter kann keinen Typ haben, der "Auto" enthält  
  
 Eine Methode oder ein Vorlagenparameter kann nicht mit dem `auto`\-Schlüsselwort deklariert werden, wenn die standardmäßige [\/Zc:auto](../../build/reference/zc-auto-deduce-variable-type.md)\-Compileroption gültig ist.  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie das `auto`\-Schlüsselwort aus der Parameterdeklaration.  
  
## Beispiel  
 Im folgenden Beispiel wird C3535 erzeugt, da ein Funktionsparameter mit dem `auto`\-Schlüsselwort deklariert und mit **\/Zc:auto** kompiliert wird.  
  
```  
// C3533a.cpp  
// Compile with /Zc:auto  
void f(auto j){} // C3533  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3535 erzeugt, da ein Vorlagenparameter mit dem `auto`\-Schlüsselwort deklariert und mit **\/Zc:auto** kompiliert wird.  
  
```  
// C3533b.cpp  
// Compile with /Zc:auto  
template<auto T> class C{}; // C3533  
```  
  
## Siehe auch  
 [Auto\-Schlüsselwort](../../cpp/auto-keyword.md)   
 [\/Zc:auto \(Variablentyp ableiten\)](../../build/reference/zc-auto-deduce-variable-type.md)