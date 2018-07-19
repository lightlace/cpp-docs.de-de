---
title: Compilerfehler C3149 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3149
dev_langs:
- C++
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c0441a7aebf86139aedbd5e45a7645db0a90b37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248507"
---
# <a name="compiler-error-c3149"></a>Compilerfehler C3149
'Typ': Dieser Typ ohne einen auf oberster Ebene 'Char' kann nicht verwenden  
  
 Eine Deklaration wurde nicht ordnungsgemäß angegeben.  
  
 Angenommen, Sie möglicherweise einen CLR-Typ im globalen Gültigkeitsbereich definiert und versucht, eine Variable des Typs als Teil der Definition zu erstellen. Da globale Variablen von CLR-Typen nicht zulässig sind, generiert der Compiler C3149 generiert.  
  
 Deklarieren Sie Variablen von CLR-Typen innerhalb einer Funktion oder eines Typs Funktionsdefinition, um diesen Fehler zu beheben.  
  
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
