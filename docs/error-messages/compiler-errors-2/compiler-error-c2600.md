---
title: Compilerfehler Fehler C2600 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2600
dev_langs:
- C++
helpviewer_keywords:
- C2600
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13b4cdf15dca9b3978f8c7855a5f1b07cc86f0b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2600"></a>Compilerfehler Fehler C2600
'Funktion': kann keine vom Compiler generierte spezielle Memberfunktion definieren (Deklaration in der ersten Klasse erforderlich)  
  
 Bevor Sie Member-Funktionen wie Konstruktoren oder Destruktoren für eine Klasse definieren können, müssen sie in der Klasse deklariert werden. Der Compiler kann standardmäßige Konstruktoren und Destruktoren (speziellen Memberfunktionen genannt) generieren, wenn keine in der Klasse deklariert werden. Wenn Sie eine dieser Funktionen ohne eine entsprechende Deklaration in der Klasse definieren, erkennt der Compiler jedoch einen Konflikt.  
  
 Beheben Sie diesen Fehler, indem Sie in der Klassendeklaration jede Member-Funktion, die Sie außerhalb der Klassendeklaration definieren, deklarieren.  
  
 Im folgenden Beispiel wird C2600 generiert:  
  
```  
// C2600.cpp  
// compile with: /c  
class C {};  
C::~C() {}   // C2600  
  
class D {  
   D::~D();  
};  
  
D::~D() {}  
```