---
title: "Compilerfehler C2872"
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
  - "C2872"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2872"
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2872
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Symbol' : Mehrdeutiges Attribut  
  
 Der Compiler kann nicht ermitteln, auf welches Symbol verwiesen wird.  
  
 C2872 kann auftreten, wenn eine Headerdatei eine [using\-Anweisung](../../misc/using-directive-cpp.md) beinhaltet und eine nachfolgende Headerdatei mit `#include` eingefügt wurde, die einen Typ enthält, der auch im angegebenen Namespace der `using`\-Direktive vorhanden ist.  Geben Sie eine `using`\-Direktive erst nach den `#include`\-Anweisungen für Ihre Headerdateien an.  
  
 Weitere Informationen zu C2872, Sie finden. [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;316317](http://support.microsoft.com/default.aspx?scid=kb;en-us;316317)  
  
 Im folgenden Beispiel wird C2872 generiert:  
  
```  
// C2872.cpp  
namespace A {  
   int i;  
}  
  
using namespace A;  
int i;  
int main() {  
   ::i++;   // ok  
   A::i++;   // ok  
   i++;   // C2872 ::i or A::i?  
}  
```