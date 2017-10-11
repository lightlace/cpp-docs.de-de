---
title: Compiler-Fehler C2743 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2743
dev_langs:
- C++
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f45e7617bbf162c23994897c42aab44abeacea88
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2743"></a>Compiler-Fehler C2743 generiert
'Typ': einen systemeigenen Typ mit __clrcall-Destruktor oder Kopierkonstruktor nicht abfangen  
  
 Ein Modul mit kompiliert **"/ CLR"** hat versucht, eine Ausnahme des systemeigenen Typs und, bei denen Destruktor des Typs oder der Kopierkonstruktor nutzt `__clrcall` Aufrufkonvention.  
  
 Beim Kompilieren mit **"/ CLR"**, Behandlung von Ausnahmen erwartet die Memberfunktionen in einem systemeigenen Typ sein [__cdecl](../../cpp/cdecl.md) und nicht [__clrcall](../../cpp/clrcall.md). Systemeigene Typen mit Memberfunktionen verwenden `__clrcall` Aufrufkonvention kann nicht aufgefangen werden, in einem Modul kompiliert mit **"/ CLR"**.  
  
 Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2743 generiert.  
  
```  
// C2743.cpp  
// compile with: /clr  
public struct S {  
   __clrcall ~S() {}  
};  
  
public struct T {  
   ~T() {}  
};  
  
int main() {  
   try {}  
   catch(S) {}   // C2743  
   // try the following line instead  
   // catch(T) {}  
  
   try {}  
   catch(S*) {}   // OK  
}  
```
