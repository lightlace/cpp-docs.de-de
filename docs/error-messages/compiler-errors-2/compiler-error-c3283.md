---
title: Compilerfehler C3283 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3283
dev_langs:
- C++
helpviewer_keywords:
- C3283
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 94b1028f19cd5ca8b490e3247d0f55cff36bb19a
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3283"></a>Compilerfehler C3283
"Typ": Eine Schnittstelle darf keinen Instanzenkonstruktor aufweisen  
  
 Eine CLR- [Schnittstelle](../../windows/interface-class-cpp-component-extensions.md) darf keinen Instanzenkonstruktor aufweisen.  Ein statischer Konstruktor ist zulässig.  
  
 Im folgenden Beispiel wird C3283 generiert:  
  
```  
// C3283.cpp  
// compile with: /clr  
interface class I {  
   I();   // C3283  
};  
```  
  
 Mögliche Lösung:  
  
```  
// C3283b.cpp  
// compile with: /clr /c  
interface class I {  
   static I(){}  
};  
```
