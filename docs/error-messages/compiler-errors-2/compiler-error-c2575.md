---
title: Compilerfehler C2575 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2575
dev_langs:
- C++
helpviewer_keywords:
- C2575
ms.assetid: 9eb45706-37ef-4481-b373-6d193ba13634
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 63e31d1cb3b6ebe7129510464732a37ae416da82
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2575"></a>Compilerfehler C2575
'Bezeichner': nur Memberfunktionen und Basen virtuell sein können  
  
 Eine globale Funktion oder Klasse deklariert wird `virtual`. Dies ist nicht zulässig.  
  
 Im folgende Beispiel wird C2575 generiert:  
  
```  
// C2575.cpp  
// compile with: /c  
virtual void func() {}   // C2575  
  
void func2() {}  
struct A {  
   virtual void func2(){}  
};  
```
