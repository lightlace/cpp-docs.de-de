---
title: Compilerfehler C3538 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3538
dev_langs:
- C++
helpviewer_keywords:
- C3538
ms.assetid: ef3698a5-7356-4c62-b9af-5d3a4baed958
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 35f852e41ff86b9eed39da0aeb367d7049b8db4b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3538"></a>Compilerfehler C3538
In einer Deklaratorliste muss "auto" immer in denselben Typ hergeleitet werden.  
  
 Nicht alle deklarierten Variablen in einer Deklarationsliste werden in den gleichen Typ aufgelöst.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass alle `auto`-Deklarationen in der Liste in denselben Typ hergeleitet werden.  
  
## <a name="example"></a>Beispiel  
 Die folgenden Anweisungen erzeugen C3538. Jede Anweisung deklariert mehrere Variablen, aber jede Verwendung des `auto`-Schlüsselworts wird nicht in den gleichen Typ abgeleitet.  
  
```  
// C3538.cpp  
// Compile with /Zc:auto  
// C3538 expected  
int main()  
{  
// Variable x1 is a pointer to char, but y1 is a double.  
   auto * x1 = "a", y1 = 3.14;    
// Variable c is a char and c1 is char*, but c2, and c3 are pointers to pointers.  
   auto c = 'a', *c1 = &c, * c2 = &c1, * c3 = &c2;   
// Variable x2 is an int, but y2 is a double and z is a char.  
   auto x2(1), y2(0.0), z = 'a';   
// Variable a is a pointer to int, but b is a pointer to double.  
   auto *a = new auto(1), *b = new auto(2.0);   
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Auto-Schlüsselwort](../../cpp/auto-keyword.md)