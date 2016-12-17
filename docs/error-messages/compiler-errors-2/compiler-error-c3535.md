---
title: "Compilerfehler C3535"
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
  - "C3535"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3535"
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3535
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Typ für "type1" kann nicht aus "type2" abgeleitet werden  
  
 Der Typ der vom `auto`\-Schlüsselwort deklarierten Variablen kann nicht aus dem Typ des Initialisierungsausdrucks abgeleitet werden.  Dieser Fehler tritt z. B. auf, wenn der Initialisierungsausdruck `void` ergibt, wobei es sich nicht um einen Typ handelt.  
  
### So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass der Typ des Initialisierungsausdrucks nicht `void` ist.  
  
2.  Stellen Sie sicher, dass die Deklaration kein Zeiger auf einen grundlegenden Typ ist.  Weitere Informationen finden Sie unter [Grundlegende Typen](../../cpp/fundamental-types-cpp.md).  
  
3.  Wenn die Deklaration ein Zeiger auf einen Typ ist, stellen Sie sicher, dass der Initialisierungsausdruck ein Zeigertyp ist.  
  
## Beispiel  
 Im folgenden Beispiel wird C3535 erzeugt, da der Initialisierungsausdruck `void` ergibt.  
  
```  
// C3535a.cpp  
// Compile with /Zc:auto  
void f(){}  
int main()  
{  
   auto x = f();   //C3535  
   return 0;  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3535 erzeugt, da die Anweisung die Variable `x` als Zeiger auf einen abgeleiteten Typ deklariert, der Initialisiererausdruck aber den Typ double aufweist.  Infolgedessen kann der Compiler den Typ der Variablen nicht ableiten.  
  
```  
// C3535b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto* x = 123.0;   // C3535  
   return 0;  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3535 erzeugt, da die Variable `p` einen Zeiger auf einen abgeleiteten Typ deklariert, der Initialisierungsausdruck aber kein Zeigertyp ist.  
  
```  
// C3535c.cpp  
// Compile with /Zc:auto  
class A { };  
A x;  
auto *p = x;  // C3535  
```  
  
## Siehe auch  
 [Auto\-Schlüsselwort](../../cpp/auto-keyword.md)   
 [Grundlegende Typen](../../cpp/fundamental-types-cpp.md)