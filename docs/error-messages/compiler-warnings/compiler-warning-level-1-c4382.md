---
title: "Compilerwarnung (Stufe 1) C4382 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4382"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4382"
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4382
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Auslösen von 'Typ': Ein Typ mit einem \_\_clrcall\-Destruktor oder einem Kopierkonstruktor kann nur in einem \/clr:pure\-Modul abgefangen werden.  
  
 Von einer mit **\/clr** \(nicht **\/clr:pure**\) kompilierten Ausnahmebehandlung wird erwartet, dass es sich bei den Memberfunktionen in einem systemeigenen Typ um [\_\_cdecl](../../cpp/cdecl.md) und nicht um [\_\_clrcall](../../cpp/clrcall.md) handelt.  Systemeigene Typen mit Memberfunktionen, die die `__clrcall`\-Aufrufkonvention verwenden, können nicht in einem mit **\/clr** kompilierten Modul abgefangen werden.  
  
 Wenn die Ausnahme in einem mit **\/clr:pure** kompilierten Modul abgefangen wird, können Sie diese Warnung ignorieren.  
  
 Weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Beispiel  
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