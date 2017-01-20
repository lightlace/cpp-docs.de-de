---
title: "Compilerwarnung (Stufe 4) C4634"
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
  - "C4634"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4634"
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4634
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

XML\-Dokumentkommentar: Kann nicht angewendet werden: Grund  
  
 XML\-Dokumentationstags können nicht auf alle C\+\+\-Konstrukte angewendet werden.  So kann z. B. einem Namespace oder einer Vorlage kein Dokumentationskommentar hinzugefügt werden.  
  
 Weitere Informationen finden Sie unter [XML\-Dokumentation](../../ide/xml-documentation-visual-cpp.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4634 generiert.  
  
```  
// C4634.cpp // compile with: /W4 /doc /c /// This is a namespace.   // C4634 namespace hello { class MyClass  {}; };  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C4634 generiert.  
  
```  
// C4634_b.cpp // compile with: /W4 /doc /c /// This is a template.   // C4634 template <class T> class MyClass  {};  
```