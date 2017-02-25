---
title: "Compilerfehler C2452 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2452"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2452"
ms.assetid: a4ec7642-6660-4c7a-9866-853d1cc67daf
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2452
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ' : Ungültiger Quelltyp für safe\_cast  
  
 Der Quelltyp für [safe\_cast](../../windows/safe-cast-cpp-component-extensions.md) war nicht gültig.  Zum Beispiel müssen alle Typen in einer `safe_cast`\-Operation CLR\-Typen sein.  
  
 Im folgenden Beispiel wird C2452 generiert:  
  
```  
// C2452.cpp  
// compile with: /clr  
  
struct A {};  
struct B : public A {};  
  
ref struct C {};  
ref struct D : public C{};  
  
int main() {  
   A a;  
   safe_cast<B*>(&a);   // C2452  
  
   // OK  
   C ^ c = gcnew C;  
   safe_cast<D^>(c);  
}  
```