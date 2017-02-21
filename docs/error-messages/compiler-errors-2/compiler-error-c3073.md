---
title: "Compilerfehler C3073 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3073"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3073"
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3073
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Die Verweisklasse hat keinen benutzerdefinierten Kopierkonstruktor  
  
 In einer [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md)\-Kompilierung generiert der Compiler keinen Kopierkonstruktor für einen Referenztyp.  Sie müssen in jeder **\/clr**\-Kompilierung einen eigenen Kopierkonstruktor für einen Referenztyp definieren, wenn eine Instanz des Typs kopiert werden soll.  
  
 Weitere Informationen finden Sie unter [C\+\+\-Stack\-Semantik für Referenztypen](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3073 generiert.  
  
```  
// C3073.cpp  
// compile with: /clr  
ref class R {  
public:  
   R(int) {}  
};  
  
ref class S {  
public:  
   S(int) {}  
   S(const S %rhs) {}   // copy constructor  
};  
  
void f(R) {}  
void f2(S) {}  
void f3(R%){}  
  
int main() {  
   R r(1);  
   f(r);   // C3073  
   f3(r);   // OK  
  
   S s(1);  
   f2(s);   // OK  
}  
```