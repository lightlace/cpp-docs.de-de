---
title: Compilerwarnung (Stufe 2) C4396 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4396
dev_langs:
- C++
helpviewer_keywords:
- C4396
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b937b6ecebedc6984279502a5f64b287f09bd2d9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290669"
---
# <a name="compiler-warning-level-2-c4396"></a>Compilerwarnung (Stufe 2) C4396
"Name": Der Inlinespezifizierer kann nicht verwendet werden, wenn eine Friend-Deklaration auf die Spezialisierung einer Funktionsvorlage verweist.  
  
 Eine Spezialisierung einer Funktionsvorlage kann nicht angegeben werden, keines der [Inline](../../cpp/inline-functions-cpp.md) Spezifizierer. Der Compiler gibt die Warnung C4396 aus und ignoriert den Inlinespezifizierer.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie den `inline`-, `__inline`- oder `__forceinline` -Spezifizierer aus der Deklaration der Friend-Funktion.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel enthält eine ungültige Friend-Funktionsdeklaration mit einem `inline` -Spezifizierer.  
  
```  
// C4396.cpp  
// compile with: /W2 /c  
  
class X;   
template<class T> void Func(T t, int i);  
  
class X {  
    friend inline void Func<char>(char t, int i);  //C4396  
// try the following line instead  
//    friend void Func<char>(char t, int i);   
    int i;  
};  
```