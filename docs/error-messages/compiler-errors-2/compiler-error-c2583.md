---
title: Compilerfehler C2583 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2583
dev_langs:
- C++
helpviewer_keywords:
- C2583
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 924a370a59fff0e118b76e52e17d44b3b2268103
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2583"></a>Compilerfehler C2583
'Bezeichner': "Const/Volatile" this-Zeiger ist ungültig für Konstruktor/Destruktor  
  
 Deklariert einen Konstruktor oder Destruktor `const` oder `volatile`. Dies ist nicht zulässig.  
  
 Im folgende Beispiel wird C2583 generiert:  
  
```  
// C2583.cpp  
// compile with: /c  
class A {  
public:  
   int i;  
   A() const;   // C2583  
  
   // try the following line instead  
   // A();  
};  
```
