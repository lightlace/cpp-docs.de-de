---
title: Compiler-Warnung (Stufe 2) C4396 aus | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4396
dev_langs:
- C++
helpviewer_keywords:
- C4396
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 84f0628de933344eb23dc6325679abdcd3699c3a
ms.openlocfilehash: 8e0538cc5a1ec9279c4d84cb9e23e0d6fabfd77e
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-2-c4396"></a>Compilerwarnung (Stufe 2) C4396
"Name": Der Inlinespezifizierer kann nicht verwendet werden, wenn eine Friend-Deklaration auf die Spezialisierung einer Funktionsvorlage verweist.  
  
 Eine Spezialisierung der Funktionsvorlage kann nicht angeben, die [Inline](../../cpp/inline-functions-cpp.md) Spezifizierer. Der Compiler gibt die Warnung C4396 aus und ignoriert den Inlinespezifizierer.  
  
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
