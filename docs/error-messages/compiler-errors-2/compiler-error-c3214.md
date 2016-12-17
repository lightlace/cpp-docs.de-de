---
title: "Compilerfehler C3214"
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
  - "C3214"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3214"
ms.assetid: 49ee4a9a-2549-4adb-9d3a-38e154303c2e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3214
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„type“: Ungültiges Typargument für generischen Parameter „param“ von „generic\_type“ \(generisch\). Die Einschränkung „constraint“ wird nicht erfüllt.  
  
 Der Typ wurde für die Instanziierung einer generischen Klasse angegeben, die die Einschränkung der generischen Klasse nicht erfüllt.  
  
 Im folgenden Beispiel wird C3214 generiert:  
  
```  
// C3214.cpp // compile with: /clr interface struct A {}; generic <class T> where T : A ref class C {}; ref class X : public A {}; int main() { C<int>^ c = new C<int>;   // C3214 C<X ^> ^ c2 = new C<X^>;   // OK }  
```