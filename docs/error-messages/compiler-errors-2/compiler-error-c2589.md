---
title: Compilerfehler C2589 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2589
dev_langs:
- C++
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c15589358979f554a9c17114f7d78b05dd83c472
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230752"
---
# <a name="compiler-error-c2589"></a>Compilerfehler C2589
'Bezeichner': Ungültiges Token auf der rechten Seite des '::'  
  
 Wenn eine Klasse, Struktur oder union Namen auf der linken Seite des Bereichsauflösungsoperators (zwei Doppelpunkte) angezeigt wird, muss das Token auf der rechten Seite eine Klasse, Struktur oder union-Member. Andernfalls kann alle globalen Bezeichner auf der rechten Seite angezeigt.  
  
 Der Bereichsauflösungsoperator kann nicht überladen werden.  
  
 Im folgende Beispiel wird C2589 generiert:  
  
```  
// C2589.cpp  
void Test(){}  
class A {};  
void operator :: ();   // C2589  
  
int main() {  
   ::Test();  
}  
```