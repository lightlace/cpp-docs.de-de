---
title: Compilerfehler C2228 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2228
dev_langs:
- C++
helpviewer_keywords:
- C2228
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 969f622877c60bdc340dedf8a2416ac56b2ad0e0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171024"
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