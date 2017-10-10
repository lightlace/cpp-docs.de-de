---
title: Compilerfehler C3073 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3073
dev_langs:
- C++
helpviewer_keywords:
- C3073
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 860cc8fccb545a8c66a8a5724b9854e9547deb10
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3073"></a>Compilerfehler C3073
'Typ': Verweisklasse verfügt nicht über einen benutzerdefinierten Kopierkonstruktor  
  
 In einem [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) Kompilierung, generiert der Compiler einen Kopierkonstruktor für einen Verweistyp nicht. In einem **"/ CLR"** Kompilierung, müssen Sie eigene Kopierkonstruktor für einen Verweistyp definieren, wenn Sie davon ausgehen, dass eine Instanz des Typs kopiert werden soll.  
  
 Weitere Informationen finden Sie unter [C++-Stapelsemantik für Referenztypen](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3073 generiert.  
  
```  
// C3073.cpp  
// compile with: /clr  
ref class R {  
public:  
   R(int) {}  
};  
  
ref class S {  
public:  
   S(int) {}  
   S(const S %rhs) {}   // copy constructor  
};  
  
void f(R) {}  
void f2(S) {}  
void f3(R%){}  
  
int main() {  
   R r(1);  
   f(r);   // C3073  
   f3(r);   // OK  
  
   S s(1);  
   f2(s);   // OK  
}  
```
