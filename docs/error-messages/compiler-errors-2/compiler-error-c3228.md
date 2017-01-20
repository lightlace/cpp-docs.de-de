---
title: "Compilerfehler C3228"
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
  - "C3228"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3228"
ms.assetid: 9015adf9-17b0-4312-b4a7-c1f33e4126f4
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3228
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': Das generische Typargument für 'param' kann nicht 'typ' sein, es muss ein Werttyp oder ein Handletyp sein  
  
 Ein falscher Typ wurde als generisches Typargument übergeben.  
  
 Im folgenden Beispiel wird C3228 generiert:  
  
```  
// C3228.cpp // compile with: /clr class A {}; value class B {}; generic <class T> void Test() {} ref class C { public: generic <class T> static void f() {} }; int main() { C::f<A>();   // C3228 C::f<B>();   // OK Test<C>();   // C3228 Test<C ^>();   // OK }  
```