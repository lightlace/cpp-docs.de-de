---
title: "Compilerfehler C2216"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C2216"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2216"
ms.assetid: 250f6bdc-a5e1-495f-a1e8-6e8e7021ad9d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2216
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Schlüsselwort1' kann nicht mit 'Schlüsselwort2' verwendet werden.  
  
 Zwei Schlüsselwörter, die sich gegenseitig ausschließen, wurden zusammen verwendet.  
  
## Beispiel  
 Im folgenden Beispiel wird C2216 generiert:  
  
```  
// C2216.cpp // compile with: /clr /c ref struct Y1 { literal static int staticConst2 = 10;   // C2216 };  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C2216 generiert:  
  
```  
// C2216b.cpp // compile with: /clr /c public ref class X { extern property int i { int get(); }   // C2216 extern not allowed on property typedef property int i2;   // C2216 typedef not allowed on property };  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C2216 generiert:  
  
```  
// C2216c.cpp // compile with: /clr /c public interface struct I { double f(); double g(); double h(); }; public ref struct R : I { virtual double f() new override { return 0.0; }   // C2216 virtual double g() new { return 0.0; }   // OK virtual double h() override { return 0.0; }   // OK };  
```