---
title: Compilerfehler C2503 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2503
dev_langs:
- C++
helpviewer_keywords:
- C2503
ms.assetid: da86cc89-fd04-400b-aa8d-a5ffaf7e3918
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1eb2f8d30d7e61dbc6fe0b4a0872046c38dbe549
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2503"></a>Compilerfehler C2503
'Klasse': Basisklassen sind keine Arrays der Größe 0 (null)  
  
 Eine Basisklasse oder die Struktur enthält ein Array der Größe 0 (null). Ein Array in einer Klasse muss mindestens ein Element aufweisen.  
  
 Im folgende Beispiel wird C2503 generiert:  
  
```  
// C2503.cpp  
// compile with: /c  
class A {  
   public:  
   int array [];  
};  
  
class B : A {};    // C2503  
  
class C {  
public:  
   int array [10];  
};  
  
class D : C {};  
```
