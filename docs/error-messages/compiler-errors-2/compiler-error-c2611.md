---
title: Compiler-Fehler C2611 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2611
dev_langs:
- C++
helpviewer_keywords:
- C2611
ms.assetid: 3f2d5253-f24f-4724-83d0-6b2aa6a4e551
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6741ce6f8d951670f44e45191d8b3658cc1c5317
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2611"></a>Compiler-Fehler C2611 generiert
'token': Unzulässiger Folgendes ' ~ "(Bezeichner)  
  
 Das Token ist kein Bezeichner.  
  
 Im folgende Beispiel wird C2611 generiert:  
  
```  
// C2611.cpp  
// compile with: /c  
class C {  
   C::~operator int();   // C2611  
   ~C();   // OK  
};  
```