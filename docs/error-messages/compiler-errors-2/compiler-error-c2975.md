---
title: Compilerfehler C2975 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2975
dev_langs:
- C++
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 07b2b96cd79364215c9a859a9fd0282768ff45e4
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2975"></a>Compilerfehler C2975
'Arg': Ungültiges Vorlagenargument für "Type", Zeitpunkt der Kompilierung konstanter Ausdruck erwartet  
  
 Das Vorlagenargument entspricht nicht der Vorlagendeklaration; Ein konstanter Ausdruck sollte in die spitzen Klammern angezeigt werden. Variablen werden als tatsächliche Vorlagenargumente nicht zulässig. Überprüfen Sie die Vorlagendefinition, um die richtigen Typen zu ermitteln.  
  
 Im folgenden Beispiel wird C2975 generiert:  
  
```  
// C2975.cpp  
template<int I>  
class X {};  
  
int main() {  
   int i = 4, j = 2;  
   X<i + j> x1;   // C2975  
   X<6> x2;   // OK  
}  
```  
  
 C2975 tritt auch bei der Verwendung von __LINE\_ \_ als eine Kompilierzeitkonstante mit [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md). Eine Lösung wäre die Kompilierung mit [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) anstelle von **/Zi**.  
  
```  
// C2975b.cpp  
// compile with: /ZI  
// processor: x86  
template<long line>   
void test(void) {}  
  
int main() {  
   test<__LINE__>();   // C2975  
}  
```