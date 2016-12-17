---
title: "Compilerfehler C2715"
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
  - "C2715"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2715"
ms.assetid: c81567a7-5b65-468f-aaf9-835f91e468e4
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2715
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ' : Auslösen oder Abfangen dieses Typs nicht möglich  
  
 Werttypen sind keine gültigen Argumente für Ausnahmebehandlungen in verwaltetem Code \(weitere Informationen unter [Exception Handling](../../windows/exception-handling-cpp-component-extensions.md)\).  
  
```  
// C2715a.cpp  
// compile with: /clr  
using namespace System;  
  
value struct V {  
   int i;  
};  
  
void f1() {  
   V v;  
   v.i = 10;  
   throw v;   // C2715  
   // try the following line instead  
   // throw ((V^)v);  
}  
  
int main() {  
   try {  
      f1();  
   }  
  
   catch(V v) { if ( v.i == 10 ) {   // C2715  
   // try the following line instead  
   // catch(V^ pv) { if ( pv->i == 10 ) {  
         Console::WriteLine("caught 10 - looks OK");  
      }   
      else {  
         Console::WriteLine("catch looks bad");  
      }  
   }  
   catch(...) {  
      Console::WriteLine("catch looks REALLY bad");  
   }  
}  
```  
  
 Bei Verwendung der Ausnahmebehandlung in Managed Extensions for C\+\+ sind [\_\_value](../../misc/value.md)\-Typen oder [\_\_gc](../../misc/gc.md)\-Zeiger keine gültigen Argumente.  Um diesen Fehler zu beheben, verwenden Sie das Schlüsselwort [\_\_box](../../misc/box.md), um das Argument mittels Boxing zu packen.  
  
 Im folgenden Beispiel wird C2715 generiert:  
  
```  
// C2715b.cpp  
// compile with: /clr:oldSyntax  
using namespace System;  
  
__value struct V {  
   int i;  
};  
  
void f1() {  
   V v;  
   v.i = 10;  
   throw v;   // C2715  
   // try the following line instead  
   // throw __box(v);  
}  
  
int main() {  
   try {  
      f1();  
   }  
  
   catch(V v) { if ( v.i == 10 ) {   // C2715  
   // try the following line instead  
   // catch(__box V *pv) { if ( pv->i == 10 ) {  
         Console::WriteLine(S"caught 10 - looks OK");  
      }   
      else {  
         Console::WriteLine(S"catch looks bad");  
      }  
   }  
   catch(...) {  
      Console::WriteLine(S"catch looks REALLY bad");  
   }  
}  
```