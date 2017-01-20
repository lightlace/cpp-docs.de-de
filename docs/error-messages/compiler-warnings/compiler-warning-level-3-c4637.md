---
title: "Compilerwarnung (Stufe 3) C4637"
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
  - "C4637"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4637"
ms.assetid: 5fd347c1-2de9-408f-9136-1bf1ff273622
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4637
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

XML\-Dokumentkommentarziel: Das \<include\>\-Tag wurde verworfen.  reason  
  
 Die Syntax eines [\<include\>](../../ide/include-visual-cpp.md)\-Tags war nicht richtig.  
  
 Im folgenden Beispiel wird C4637 generiert:  
  
```  
// C4637.cpp // compile with: /clr /doc /LD /W3 using namespace System; /// Text for class MyClass. public ref class MyClass { public: /// <include file="c:\davedata\jtest\xml_include.doc"/> // Try the following line instead: // /// <include file='xml_include.doc' path='MyDocs/MyMembers/*' /> void MyMethod() { } };   // C4637  
```