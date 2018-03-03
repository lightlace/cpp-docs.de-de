---
title: Compilerfehler C3821 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3821
dev_langs:
- C++
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eda98ddd6247a2b3d137c015e5e4e3b06f04d821
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3821"></a>Compilerfehler C3821
'Funktion': verwaltete Typ oder die Funktion kann nicht in eine nicht verwaltete Funktion verwendet werden  
  
 Funktionen mit Inlineassembly oder [Setjmp](../../c-runtime-library/reference/setjmp.md) Werttypen oder verwaltete Klassen sind nicht zulässig. Um diesen Fehler zu beheben, entfernen Sie die Inlineassembly und `setjmp` oder entfernen Sie die verwalteten Objekte.  
  
 C3821 kann auch auftreten, wenn Sie versuchen, die automatische Speicherung in einer Vararg-Funktion verwenden.  Weitere Informationen finden Sie unter [Variablenargumentlisten (...) (C + C++ / CLI) ](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md) und [C++-Stapelsemantik für Referenztypen](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3821 generiert.  
  
```  
// C3821a.cpp  
// compile with: /clr /c  
public ref struct R {};  
void test1(...) {  
   R r;   // C3821  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3821 generiert.  
  
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
