---
title: Compiler-Fehler C3821 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3821
dev_langs:
- C++
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
caps.latest.revision: 12
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
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 24212b0df7b665f8c8ab2614b9a23e66f19586af
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3821"></a>Compilerfehler C3821
'Funktion': nicht verwaltete Typ oder die Funktion in eine nicht verwaltete Funktion verwendet werden  
  
 Funktionen mit Inlineassembly oder [Setjmp](../../c-runtime-library/reference/setjmp.md) können keine Werttypen oder verwaltete Klassen enthalten. Um diesen Fehler zu beheben, entfernen Sie die Inlineassembly und `setjmp` oder die verwalteten Objekte.  
  
 C3821 kann auch auftreten, wenn Sie versuchen, die automatische Speicherung in einer Vararg-Funktion verwenden.  Weitere Informationen finden Sie unter [Variablenargumentlisten (...) (C++ / CLI) ](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md) und [C++-Stack-Semantik für Referenztypen](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3821 generiert.  
  
```  
// C3821a.cpp  
// compile with: /clr /c  
public ref struct R {};  
void test1(...) {  
   R r;   // C3821  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3821 generiert.  
  
```  
// C3821b.cpp  
// compile with: /clr  
// processor: /x86  
ref class A {  
   public:  
   int i;  
};  
  
int main() {  
   // cannot use managed classes in this function  
   A ^a;     
  
   __asm {  
      nop  
   }  
} // C3821  
```  

