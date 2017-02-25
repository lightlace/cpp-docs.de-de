---
title: "Compilerfehler C3609 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3609"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3609"
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C3609
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„Member“: Eine versiegelte oder endgültige Funktion muss virtuell sein.  
  
 Die [sealed](../../windows/sealed-cpp-component-extensions.md)\- und [final](../../cpp/final-specifier.md)\-Schlüsselwörter sind nur bei einer Klasse, Struktur oder Memberfunktion zulässig, die als `virtual` gekennzeichnet sind.  
  
 Im folgenden Beispiel wird C3609 generiert:  
  
```  
// C3609.cpp  
// compile with: /clr /c  
ref class C {  
   int f() sealed;   // C3609  
   virtual int f2() sealed;   // OK  
};  
```  
  
 **Verwaltete Erweiterungen für C\+\+**  
  
 Im folgenden Beispiel wird C3609 generiert:  
  
```  
// C3609c.cpp  
// compile with: /clr:oldSyntax /c  
__gc class C {  
   __sealed int f();   // C3609  
   __sealed virtual int f2();   // OK  
};  
```