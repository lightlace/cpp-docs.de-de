---
title: "Compilerfehler C2726"
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
  - "C2726"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2726"
ms.assetid: f0191bb7-c175-450b-bf09-a3213db96d09
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2726
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"gcnew" kann nur zum Erstellen eines Objekts mit verwaltetem oder WinRT\-Typ verwendet werden.  
  
 Sie können keine Instanz eines systemeigenen Typs auf dem Heap der Garbage Collection erstellen.  
  
 Im folgenden Beispiel wird C2726 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2726.cpp  
// compile with: /clr  
using namespace System;  
class U {};  
ref class V {};  
value class W {};  
  
int main() {  
   U* pU = gcnew U;    // C2726  
   U* pU2 = new U;   // OK  
   V^ p2 = gcnew V;   // OK  
   W p3;   // OK  
  
}  
```  
  
 Im folgenden Beispiel wird C2726 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2726b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
class U {};  
__gc class V {};  
  
int main() {  
   U* pU = __gc new U;    // C2726  
   U* pU2 = new U;    // OK  
   V* p2 = __gc new V;  
}  
```