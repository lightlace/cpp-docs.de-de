---
title: Compilerfehler C2586 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2586
dev_langs:
- C++
helpviewer_keywords:
- C2586
ms.assetid: dae703c7-5c38-4db6-8411-4d1b22713eb5
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c98f9a9f5e5f16cec23c8bc6de7efda7a7ce473d
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2586"></a>Compilerfehler C2586
Unzulässige benutzerdefinierte Konvertierungssyntax: Ungültige Dereferenzierungen  
  
 Dereferenzierung eines Konvertierungsoperators ist nicht zulässig.  
  
 Im folgende Beispiel wird C2586 generiert:  
  
```  
// c2586.cpp  
// compile with: /c  
struct C {  
   * operator int();   // C2586  
   operator char();   // OK  
};  
```
