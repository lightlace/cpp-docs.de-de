---
title: Compilerfehler C2514 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2514
dev_langs:
- C++
helpviewer_keywords:
- C2514
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f91dfffe27127cfbff20d7b2e67d097b65cae358
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2514"></a>Compilerfehler C2514
'Klasse': Klasse besitzt keine Konstruktoren  
  
 Die Klasse, Struktur oder Union verfügt über keinen Konstruktor mit einer Parameterliste, die den Parametern, die verwendet wird, um sie zu instanziieren übereinstimmt.  
  
 Eine Klasse muss vollständig deklariert werden, bevor es instanziiert werden kann.  
  
 Im folgende Beispiel wird C2514 generiert:  
  
```  
// C2514.cpp  
// compile with: /c  
class f;  
  
class g {  
public:  
    g (int x);  
};  
  
class fmaker {  
   f *func1() {  
      return new f(2);   // C2514  
   }  
  
   g *func2() {  
      return new g(2);   // OK  
   }  
};   
```
