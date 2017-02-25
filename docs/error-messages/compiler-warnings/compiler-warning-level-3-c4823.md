---
title: "Compilerwarnung (Stufe 3) C4823 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4823"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4823"
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Compilerwarnung (Stufe 3) C4823
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion' verwendet einen festen Zeiger, die Entladesemantik ist aber nicht aktiviert.Verwenden Sie evtl. \/EHa  
  
 Um die Fixierung eines Objekts auf dem verwalteten Heap aufzuheben, auf das von einem festen, in einem Blockbereich deklarierten Zeiger verwiesen wird, simuliert der Compiler das Verhalten von Destruktoren für lokale Klassen und "gibt quasi vor", dass der feste Zeiger über einen Destruktor verfügt, durch den der Zeiger zu einem NULL\-Zeiger wird.  Damit nach dem Auslösen einer Ausnahme ein Destruktor aufgerufen werden kann, muss die Objektentladung aktiviert werden, was durch die Verwendung von [\/EHsc](../../build/reference/eh-exception-handling-model.md) ermöglicht wird.  
  
 Sie können die Fixierung des Objekts auch manuell aufheben und die Warnmeldung ignorieren.  
  
## Beispiel  
 Im folgenden Beispiel wird C4823 generiert.  
  
```  
// C4823.cpp  
// compile with: /clr /W3 /EHa-  
using namespace System;  
  
ref struct G {  
   int m;  
};  
  
void f(G ^ pG) {  
   try {  
      pin_ptr<int> p = &pG->m;  
      // manually unpin, ignore warning  
      // p = nullptr;  
      throw gcnew Exception;  
   }  
   catch(Exception ^) {}  
}   // C4823 warning  
  
int main() {  
   f( gcnew G );  
}  
```  
  
## Beispiel  
 C4823 kann auch bei Verwendung von **\/clr:oldSyntax** generiert werden.  Im folgenden Beispiel wird C4823 generiert.  
  
```  
// C4823_b.cpp  
// compile with: /clr:oldSyntax /W3 /EHa-  
using namespace System;  
  
__gc struct G {  
   int m;  
};  
  
void f(G* pG) {  
   try {  
      int __pin* p = &pG->m;  
      // manually unpin, ignore warning  
      // p = 0;  
      throw new Exception;  
   }  
   catch(Exception*) {}  
}   // C4823  
  
int main() {  
   f( new G );  
}  
```