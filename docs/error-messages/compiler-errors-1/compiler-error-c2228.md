---
title: Compilerfehler C2228 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2228
dev_langs:
- C++
helpviewer_keywords:
- C2228
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6960d2a34a6a68925e04e0812730025d1ce2ff92
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2228"></a>Compilerfehler C2228
Links von '.identifier' muss eine Klasse/Struktur/Union stehen  
  
 Der Operand links vom Punktoperator (.) ist eine Klasse, Struktur oder Union.  
  
 Im folgenden Beispiel wird C2228 generiert:  
  
```  
// C2228.cpp  
int i;  
struct S {  
public:  
    int member;  
} s, *ps = &s;  
  
int main() {  
   i.member = 0;   // C2228 i is not a class type  
   ps.member = 0;  // C2228 ps is a pointer to a structure  
  
   s.member = 0;   // s is a structure type  
   ps->member = 0; // ps points to a structure S  
}  
```  
  
 Dieser Fehler wird auch angezeigt, wenn Sie bei der Verwendung von Managed Extensions fehlerhafte Syntax verwenden. Während Sie in anderen Visual Studio-Sprachen den Punktoperator für den Zugriff auf ein Member einer verwalteten Klasse verwenden können, bedeutet ein Zeiger auf das Objekt in C++, dass Sie den Operator '->' für den Zugriff auf das Member verwenden müssen:  
  
 Falsch: `String * myString = checkedListBox1->CheckedItems->Item[0].ToString();`  
  
 Richtig: `String * myString = checkedListBox1->CheckedItems->Item[0]->ToString();`