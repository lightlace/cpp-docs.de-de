---
title: Compilerfehler C2355 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2355
dev_langs:
- C++
helpviewer_keywords:
- C2355
ms.assetid: 0a947881-d61f-4f98-8409-32140f39500b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b88bf1619a003faa57d1fe1d4f03219267481d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2355"></a>Compilerfehler C2355
'this': Nur innerhalb nicht statischer Memberfunktionen verfügbar oder nicht statischer Datenmemberinitialisierer verfügbar.  
  
 Der `this`-Zeiger ist nur für nicht statische Memberfunktionen oder in nicht statischen Datenmemberinitialisierern gültig. Dieser Fehler kann auftreten, wenn der Klassenbereich einer Memberfunktionsdefinition außerhalb der Klasse nicht entsprechend qualifiziert wird. Der Fehler kann auch auftreten, wenn der `this`-Zeiger in einer Funktion verwendet wird, die nicht in der Klasse deklariert wird.  
  
 Stellen Sie zum Beheben dieses Problems sicher, dass die Memberfunktionsdefinition mit einer Memberfunktionsdeklaration in der Klasse übereinstimmt und dass sie nicht statisch deklariert wird. Stellen Sie für die Datenmemberinitialisierer sicher, dass das Datenmember nicht statisch deklariert wird.  
  
 Im folgenden Beispiel wird C2355 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2355.cpp  
// compile with: /c  
class MyClass {};  
MyClass *p = this;   // C2355  
  
// OK  
class MyClass2 {  
public:  
   void Test() {  
      MyClass2 *p = this;  
   }  
};  
```