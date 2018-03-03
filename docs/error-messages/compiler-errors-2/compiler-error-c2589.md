---
title: Compilerfehler C2589 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2589
dev_langs:
- C++
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d0c75c6c42bcaa60f95e6f7e5214bb28ce72f65f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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