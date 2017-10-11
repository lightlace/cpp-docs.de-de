---
title: Compilerfehler C2563 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2563
dev_langs:
- C++
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8fe3ca54a90b91151288076fd657752e3195e318
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

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
