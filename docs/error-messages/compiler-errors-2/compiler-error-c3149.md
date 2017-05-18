---
title: Compilerfehler C3149 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3149
dev_langs:
- C++
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 555b3a7ac8e0d1e5de8eacd763c9ee63101e5b78
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3149"></a>Compilerfehler C3149
'Typ': Dieser Typ ohne einen auf der obersten Ebene 'Char' kann nicht verwenden  
  
 Eine Deklaration wurde nicht ordnungsgemäß angegeben.  
  
 Angenommen, Sie möglicherweise einen CLR-Typ im globalen Gültigkeitsbereich definiert und versucht, eine Variable des Typs als Teil der Definition zu erstellen. Da globale Variablen von CLR-Typen nicht zulässig sind, generiert der Compiler C3149 generiert.  
  
 Um diesen Fehler zu beheben, deklarieren Sie Variablen von CLR-Typen innerhalb einer Funktion oder Typdefinition.  
  
 Im folgende Beispiel wird C3149 generiert:  
  
```  
// C3149.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   // declare an array of value types   
   array< Int32 ^> IntArray;   // C3149  
   array< Int32>^ IntArray2;   // OK  
}  
```  
  
 Im folgende Beispiel wird C3149 generiert:  
  
```  
// C3149b.cpp  
// compile with: /clr /c  
delegate int MyDelegate(const int, int);  
void Test1(MyDelegate m) {}   // C3149  
void Test2(MyDelegate ^ m) {}   // OK  
```  

