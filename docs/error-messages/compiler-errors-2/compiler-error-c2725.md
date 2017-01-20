---
title: "Compilerfehler C2725"
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
  - "C2725"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2725"
ms.assetid: 13cd5b1b-e906-4cd8-9b2b-510d587c665a
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2725
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'exception': Auslösen oder Erfassen eines verwalteten oder WinRT\-Objekts nach Wert oder Verweis nicht möglich  
  
 Der Typ einer verwalteten oder WinRT\-Ausnahme war falsch.  
  
## Beispiel  
 Im folgenden Beispiel wird C2725 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2725.cpp  
// compile with: /clr  
ref class R {  
public:  
   int i;  
};  
  
int main() {  
   R % r1 = *gcnew R;  
   throw r1;   // C2725  
  
   R ^ r2 = gcnew R;  
   throw r2;   // OK     
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C2725 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2725b.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   try {}  
   catch( System::Exception%) {}   // C2725  
   // try the following line instead  
   // catch( System::Exception ^e) {}  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C2725 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2725c.cpp  
// compile with: /clr:oldSyntax  
using namespace System;  
int main() {  
   try {}  
   catch( System::Exception&) {}   // C2725  
   // try the following line instead  
   // catch( System::Exception *e) {}  
}  
```