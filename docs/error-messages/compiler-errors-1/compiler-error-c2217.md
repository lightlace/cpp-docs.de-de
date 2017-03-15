---
title: "Compilerfehler C2217 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2217"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2217"
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2217
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Attribut1' erfordert 'Attribut2'  
  
 Das erste Funktionsattribut erfordert auch die Verwendung des zweiten Attributs.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Als `near` deklarierte \(`__interrupt`\) Interruptfunktion.  Interruptfunktionen müssen als `far` deklariert sein.  
  
2.  Eine Interruptfunktion wurde mit `__stdcall` oder `__fastcall` deklariert.  Diese Funktionen müssen die C\-Aufrufkonvention verwenden.  
  
## Beispiel  
 C2217 kann auch auftreten, wenn Sie einen Delegaten an eine CLR\-Funktion binden, die eine variable Anzahl von Argumenten akzeptiert.  Wenn die Funktion auch über eine Parameterarrayüberladung verfügt, verwenden Sie stattdessen diese.  Im folgenden Beispiel wird C2217 generiert.  
  
```  
// C2217.cpp  
// compile with: /clr  
using namespace System;  
delegate void MyDel(String^, Object^, Object^, ...);   // C2217  
delegate void MyDel2(String ^, array<Object ^> ^);   // OK  
  
int main() {  
   MyDel2^ wl = gcnew MyDel2(Console::WriteLine);  
   array<Object ^ > ^ x = gcnew array<Object ^>(2);  
   x[0] = safe_cast<Object^>(0);  
   x[1] = safe_cast<Object^>(1);  
  
   // wl("{0}, {1}", 0, 1);  
   wl("{0}, {1}", x);  
}  
```