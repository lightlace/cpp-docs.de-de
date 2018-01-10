---
title: Compilerfehler Fehler C2600 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2600
dev_langs: C++
helpviewer_keywords: C2600
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 407598a68df37aa130ce26e4f02e98de975ab527
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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