---
title: Compilerfehler C2563 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2563
dev_langs:
- C++
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 85a4de195c681ce8d11b789a9aca102629cc2bac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2563"></a>Compilerfehler C2563
übereinstimmende Datentypen in der Liste formaler parameter  
  
 Die Liste der formalen Parameter einer Funktion (oder ein Zeiger auf eine Funktion) stimmt nicht mit einer anderen Funktion (oder Zeiger auf eine Memberfunktion) überein. Daher kann die Zuweisung von Funktionen oder Zeiger vorgenommen werden.  
  
 Im folgende Beispiel wird C2563 generiert:  
  
```  
// C2563.cpp  
void func( int );  
void func( int, int );  
int main() {  
   void *fp();  
   fp = func;   // C2563  
}  
```