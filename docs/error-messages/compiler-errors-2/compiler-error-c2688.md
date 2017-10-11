---
title: Compiler-Fehler C2688 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2688
dev_langs:
- C++
helpviewer_keywords:
- C2688
ms.assetid: 168c9e9d-8f65-4664-af86-db71d3e6ee46
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: eaacdb4c7404dd370de31ad1bca6c07391279584
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2688"></a>Compiler-Fehler C2688 generiert
"C2:: fgrv": covariant-Rückgaben mit mehreren oder virtuelle Vererbung für Varargs-Funktionen nicht unterstützt.  
  
 Covariant-Rückgabetypen werden in Visual C++ nicht unterstützt, wenn eine Funktion mit Variable Argumenten enthält.  
  
 Zum Beheben dieses Fehlers entweder definieren Sie Funktionen, sodass sie nicht Variablenargumente verwenden oder stellen die Rückgabewerte für alle virtuellen Funktionen identisch.  
  
 Im folgende Beispiel wird C2688 generiert:  
  
```  
// C2688.cpp  
struct G1 {};  
struct G2 {};  
struct G3 : G1, G2 {};  
struct G4 {};  
struct G5 {};  
struct G6 : G4, G5 {};  
struct G7 : G3, G6 {};  
  
struct C1 {  
   virtual G4& fgrv(int,...);  
};  
  
struct C2 : C1 {  
   virtual G7& fgrv(int,...);   // C2688, does not return G4&  
};  
```
