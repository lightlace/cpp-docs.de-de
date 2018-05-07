---
title: Compilerfehler C2593 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2593
dev_langs:
- C++
helpviewer_keywords:
- C2593
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e419416266e0e3c4ebff8190b3b26b1c43c9ba0f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2593"></a>Compilerfehler C2593
'Operator Bezeichner' ist mehrdeutig  
  
 Mehr als einen möglichen Operator wird für einen überladenen Operator definiert.  
  
 Dieser Fehler möglicherweise behoben werden, wenn Sie eine explizite Umwandlung auf mindestens einen tatsächlichen Parameter verwenden.  
  
 Im folgende Beispiel wird C2593 generiert:  
  
```  
// C2593.cpp  
struct A {};  
struct B : A {};  
struct X {};  
struct D : B, X {};  
void operator+( X, X );  
void operator+( A, B );  
D d;  
  
int main() {  
   d +  d;         // C2593, D has an A, B, and X   
   (X)d + (X)d;    // OK, uses operator+( X, X )  
}  
```  
  
 Dieser Fehler kann verursacht werden, durch die Serialisierung einer Gleitkommazahl Variable mit einem `CArchive` Objekt. Der Compiler identifiziert die `<<` Operator als mehrdeutig. Die einzigen primitiven C++-Typen, `CArchive` serialisieren kann sind die Typen mit fester Größe `BYTE`, `WORD`, `DWORD`, und `LONG`. Alle ganzzahligen Typen müssen für die Serialisierung in einem dieser Typen umgewandelt werden. Gleitkommatypen müssen archiviert werden, mithilfe der `CArchive::Write()` Memberfunktion.  
  
 Im folgende Beispiel wird gezeigt, wie eine Gleitkommavariable archivieren (`f`) Archiv `ar`:  
  
```  
ar.Write(&f, sizeof( float ));  
```