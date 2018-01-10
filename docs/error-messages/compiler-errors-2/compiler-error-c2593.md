---
title: Compilerfehler C2593 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2593
dev_langs: C++
helpviewer_keywords: C2593
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 675c929995e7b0c4043586cf081343136d8e7a5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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