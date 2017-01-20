---
title: "Compilerfehler C2228"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C2228"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2228"
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2228
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Links von '.identifier' muss eine Klasse\/Struktur\/Union stehen  
  
 Der Operand links vom Punktoperator \(.\) ist keine Klasse, Struktur oder Union.  
  
 Im folgenden Beispiel wird C2228 generiert:  
  
```  
// C2228.cpp int i; struct S { public: int member; } s, *ps = &s; int main() { i.member = 0;   // C2228 i is not a class type ps.member = 0;  // C2228 ps is a pointer to a structure s.member = 0;   // s is a structure type ps->member = 0; // ps points to a structure S }  
```  
  
 Dieser Fehler wird auch angezeigt, wenn Sie bei der Verwendung von Managed Extensions fehlerhafte Syntax verwenden. Während Sie in anderen Visual Studio\-Sprachen den Punktoperator für den Zugriff auf ein Member einer verwalteten Klasse verwenden können, bedeutet ein Zeiger auf das Objekt in C\+\+, dass Sie den Operator '\-\>' für den Zugriff auf das Member verwenden müssen:  
  
 Falsch: `String * myString = checkedListBox1->CheckedItems->Item[0].ToString();`  
  
 Richtig: `String * myString = checkedListBox1->CheckedItems->Item[0]->ToString();`