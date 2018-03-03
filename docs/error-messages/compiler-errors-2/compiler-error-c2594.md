---
title: Compilerfehler C2594 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2594
dev_langs:
- C++
helpviewer_keywords:
- C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d4cca18672aad77e051ff4428dc115c53cd5ddad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2594"></a>Compilerfehler C2594
'Operator': mehrdeutige Konvertierungen von "Typ1" in "Typ2"  
  
 Keine Konvertierung von *Typ1* auf *Typ2* wurde eine direktere als alle anderen Werte. Wir empfehlen zwei mögliche Lösungen für die Konvertierung von *Typ1* auf *Typ2*. Die erste Möglichkeit besteht, definieren Sie eine direkte Konvertierung vom *Typ1* auf *Typ2*, und die zweite Möglichkeit ist die Angabe eine Sequenz von Konvertierungen von *Typ1* auf  *Typ2*.  
  
 Im folgende Beispiel wird C2594 generiert. Die vorgeschlagene Lösung des Fehlers ist eine Sequenz von Konvertierungen:  
  
```  
// C2594.cpp  
// compile with: /c  
struct A{};  
struct I1 : A {};  
struct I2 : A {};  
struct D : I1, I2 {};  
  
A *f (D *p) {  
   return (A*) (p);    // C2594  
  
// try the following line instead  
// return static_cast<A *>(static_cast<I1 *>(p));  
}  
```