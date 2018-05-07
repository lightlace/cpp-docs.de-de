---
title: Compilerfehler C3539 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3539
dev_langs:
- C++
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1f704bd283ab5228a8988d587707e978aa5b49e1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3539"></a>Compilerfehler C3539
'Typ': ein Vorlagenargument nicht mit einem Typ, der "auto" enthält  
  
 Die angegebene Vorlage Argument darf nicht enthalten eine Verwendung von der `auto` Schlüsselwort.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Geben Sie keine Vorlagenarguments mit dem `auto` Schlüsselwort.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel ergibt C3539.  
  
```  
// C3539.cpp  
// Compile with /Zc:auto  
template<class T> class C{};  
int main()  
{  
   C<auto> c;   // C3539  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Auto-Schlüsselwort](../../cpp/auto-keyword.md)