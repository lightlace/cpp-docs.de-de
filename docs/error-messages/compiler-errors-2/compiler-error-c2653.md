---
title: Compiler-Fehler C2653 | Microsoft-Dokumentation
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: eb0c1bf407d1478451c246cf615d031ef6c45bf9
ms.openlocfilehash: 2203cf8a09dbb05f6145ed238ab9fc03e458aaa5
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2653"></a>Compiler-Fehler C2653
'Bezeichner': ist keine Klasse oder Namespace  
  
Die Syntax erfordert eine Klasse, Struktur, Union oder Namespacename.  
  
Im folgende Beispiel wird C2653 generiert:  
  
```cpp  
// C2653.cpp  
// compile with: /c  
class yy {  
   void func1(int i);  
};  
  
void xx::func1(int m) {}   // C2653  
void yy::func1(int m) {}   // OK  
```  
  
C2653 ist auch möglich, wenn Sie versuchen, Sie definieren eine *zusammengesetzten Namespace*, einen Namespace, einen oder mehrere Bereich geschachtelten Namespacenamen enthält, wenn Sie eine Version von Visual C++ vor Visual Studio 2015 Update 3 verwenden. Zusammengesetzte Namespace Definitionen in C++ vor C ++&17; sind unzulässig. Ab Visual C++ 2015 Update 3 unterstützt der Compiler zusammengesetzten Namespacedefinitionen bei der [/std:c ++ neueste](../../build/reference/std-specify-language-standard-version.md) -Compileroption angegeben wird:  
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
