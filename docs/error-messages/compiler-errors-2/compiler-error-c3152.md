---
title: "Compilerfehler C3152"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C3152"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3152"
ms.assetid: 4ee6e2cd-5d19-4b73-833d-765c35797e4b
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3152
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'construct' : 'keyword' kann nur auf eine Klasse, Struktur oder virtuelle Memberfunktion angewendet werden.  
  
 Bestimmte Schlüsselwörter können nur auf eine C\+\+\-Klasse angewendet werden.  
  
 Im folgenden Beispiel wird C3152 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3152.cpp  
// compile with: /clr /c  
ref class C {  
   int (*pfn)() sealed;   // C3152  
   virtual int g() sealed;   // OK  
};  
```  
  
 Im folgenden Beispiel wird C3152 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3152_2.cpp  
// compile with: /clr:oldSyntax /c  
__value __interface A {};   // C3152;  
__value class X {};   // OK  
```