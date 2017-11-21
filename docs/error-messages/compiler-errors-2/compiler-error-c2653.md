---
title: Compilerfehler Fehler C2653 | Microsoft Docs
ms.custom: 
ms.date: 11/16/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2653
dev_langs: C++
helpviewer_keywords: C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b2cca7e855256e9caf5a72e6f8b4a6e2924eca6
ms.sourcegitcommit: 78f3f8208d49b7c1d87f4240f4a1496b7c29333e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
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
  
C2653 ist auch möglich, wenn Sie versuchen, Sie definieren eine *zusammengesetzten Namespace*, einen Namespace, eine oder mehrere Bereich geschachtelten Namespace-Namen, enthält, wenn Sie eine Version von Visual C++ vor Visual Studio 2015 Update 3 verwenden. Zusammengesetzte Namespace Definitionen in C++ vor C ++ 17 sind nicht zulässig. Ab Visual C++ 2015 Version 15.5, unterstützt der Compiler zusammengesetzten Namespacedefinitionen bei der [/std:c ++ 17](../../build/reference/std-specify-language-standard-version.md) -Compileroption angegeben ist:  
```cpp  
// C2653b.cpp  
namespace a::b {int i;}   // C2653 prior to Visual C++ 2015 Update 3,  
                          // C2429 thereafter. Use /std:c++17 to fix (or /std:c++latest in 15.3)
namespace a {  
   namespace b {  
      int i;  
   }  
}  
  
int main() {  
   a::b::i = 2;  
}  
```  

In Visual Studio 2017 Version 15.3, die /std:c ++ neueste Schalter ist erforderlich.
