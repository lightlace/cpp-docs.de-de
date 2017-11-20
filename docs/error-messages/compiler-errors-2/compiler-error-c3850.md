---
title: Compilerfehler C3850 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3850
dev_langs:
- C++
helpviewer_keywords:
- C3850
ms.assetid: 028f3a37-f3ad-4ebc-9168-3cdea47524d4
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 86d286b31d8ac9255af6f6d20400213f39576a47
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3850"></a>Compilerfehler C3850
"char": Ein universeller Zeichenname gibt ein ungültiges Zeichen an.  
  
 Zeichen, die als universelle Zeichennamen dargestellt werden, müssen gültigen Unicode-Codepunkten im Bereich 0-10FFFF entsprechen. Ein universeller Zeichenname darf weder einen Wert im Unicode-Ersatzbereich, D800-DFFF, noch ein codiertes Ersatzzeichenpaar enthalten. Der Compiler generiert das Ersatzpaar automatisch aus einem gültigen Codepunkt.  
  
 In Code, der als C kompiliert wird, darf ein universeller Zeichenname kein Zeichen im Bereich 0000-009F (inklusive) darstellen. Die einzigen Ausnahmen hierzu sind 0024 ('$'), 0040 ('@') und 0060 ('`').  
  
 In Code, der als C++ kompiliert wird, darf für einen universellen Zeichennamen jeder gültige Unicode-Codepunkt in einer Zeichenfolge oder in einem Zeichenliteral verwendet werden. Außerhalb eines Literals darf ein universeller Zeichenname weder Steuerzeichen in den Bereichen 0000-001F und 007F-009F (beide inklusive) oder ein Member des grundlegenden Quellzeichensatzes darstellen.  Weitere Informationen finden Sie unter [Character Sets](../../cpp/character-sets2.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3850 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```cpp  
// C3850.cpp  
int main() {  
   int \u0019 = 0;   // C3850, not in allowed range for an identifier  
   const wchar_t * wstr_bad  = L"\UD840DC8A"; // C3850, UCN is surrogate pair  
   const wchar_t * wstr_good = L"\U0002008A"; // Okay, UCN is valid code point  
}  
```