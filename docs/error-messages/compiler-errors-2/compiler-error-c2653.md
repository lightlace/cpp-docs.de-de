---
title: Compilerfehler Fehler C2653 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2653
dev_langs:
- C++
helpviewer_keywords:
- C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cc7990614283a20e9d07f52187258dbccad7c075
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2653"></a>Compilerfehler Fehler C2653
'Bezeichner': ist kein Name für eine Klasse oder Namespace  
  
Die Syntax ist erforderlich, eine Klasse, Struktur, Union oder Namespacename.  
  
Im folgenden Beispiel wird C2653 generiert:  
  
```cpp  
// C2653.cpp  
// compile with: /c  
class yy {  
   void func1(int i);  
};  
  
void xx::func1(int m) {}   // C2653  
void yy::func1(int m) {}   // OK  
```  
  
C2653 ist auch möglich, wenn Sie versuchen, Sie definieren eine *zusammengesetzten Namespace*, einen Namespace, eine oder mehrere Bereich geschachtelten Namespace-Namen, enthält, wenn Sie eine Version von Visual C++ vor Visual Studio 2015 Update 3 verwenden. Zusammengesetzte Namespace Definitionen in C++ vor C ++ 17 sind nicht zulässig. Ab Visual C++ 2015 Update 3, unterstützt der Compiler zusammengesetzten Namespacedefinitionen bei der [/std:c ++ neueste](../../build/reference/std-specify-language-standard-version.md) -Compileroption angegeben ist:  
```cpp  
// C2653b.cpp  
namespace a::b {int i;}   // C2653 prior to Visual C++ 2015 Update 3,  
                          // C2429 thereafter. Use /std:c++latest to fix.
namespace a {  
   namespace b {  
      int i;  
   }  
}  
  
int main() {  
   a::b::i = 2;  
}  
```  
