---
title: Compilerfehler Fehler C2758 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2758
dev_langs:
- C++
helpviewer_keywords:
- C2758
ms.assetid: 1d273034-194c-4926-9869-142d1b219cbe
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f694df9f39edbc257b887bcfd9bd13a0ba31a1a0
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2758"></a>Compilerfehler Fehler C2758
'member': Ein Member eines Verweistyps muss initialisiert werden  
  
 Der Compilerfehler C2758 wird ausgelöst, wenn der Konstruktor ein Member des Verweistyps in einer Initialisiererliste nicht initialisiert. Der Compiler lässt das Member undefiniert. Verweismembervariablen müssen initialisiert werden, wenn sie deklariert werden, oder sie müssen einen Wert in der Initialisierungsliste des Konstruktors erhalten.  
  
 Im folgenden Beispiel wird C2758 generiert:  
  
```  
// C2758.cpp  
// Compile by using: cl /W3 /c C2758.cpp  
struct A {  
   const int i;  
  
   A(int n) { };   // C2758  
   // try the following line instead  
   // A(int n) : i{n} {};  
};  
```
