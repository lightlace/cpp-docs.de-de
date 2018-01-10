---
title: Compilerwarnung (Stufe 1) C4382 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4382
dev_langs: C++
helpviewer_keywords: C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4b0cef09795553759487e28ef61babe75b35ce03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4382"></a>Compilerwarnung (Stufe 1) C4382
Auslösen von 'Typ': ein Typ mit __clrcall-Destruktor oder Kopierkonstruktor nur in "/ CLR" abgefangen werden kann: pure-Modul  
  
 Die **/CLR: pure** -Compileroption in Visual Studio 2015 als veraltet markiert ist.  
  
 Beim Kompilieren mit **"/ CLR"** (nicht **/CLR: pure**), Ausnahmebehandlung erwartet die Memberfunktionen in einem systemeigenen Typ sein [__cdecl](../../cpp/cdecl.md) und nicht [__clrcall](../../cpp/clrcall.md). Systemeigene Typen mit Memberfunktionen verwenden `__clrcall` Aufrufkonvention kann nicht aufgefangen werden, in einem Modul kompiliert mit **"/ CLR"**.  
  
 Wenn in einem Modul kompiliert werden, mit der Ausnahme abgefangen wird **/CLR: pure**, können Sie diese Warnung ignorieren.  
  
 Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4382 generiert.  
  
```  
// C4382.cpp  
// compile with: /clr /W1 /c  
struct S {  
   __clrcall ~S() {}  
};  
  
struct T {  
   ~T() {}  
};  
  
int main() {  
   S s;  
   throw s;   // C4382  
  
   S * ps = &s;  
   throw ps;   // OK  
  
   T t;  
   throw t;   // OK  
}  
```