---
title: Compilerfehler Fehler C2600 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2600
dev_langs:
- C++
helpviewer_keywords:
- C2600
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1fe5383e17212b21c11394c6b987e92aacbe637e
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

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
