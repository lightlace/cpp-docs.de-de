---
title: Compilerfehler C3452 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3452
dev_langs:
- C++
helpviewer_keywords:
- C3452
ms.assetid: e5293dcf-cb70-4133-ae2a-0bb496950ba0
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0ff18842af11d82d28819b01cb7798a4ae49eff1
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3452"></a>Compilerfehler C3452
Der Listenargumentmember ist keine Konstante.  
  
 Ein Argument wurde an ein Attribut übergeben, das eine Konstante erwartet hat, d. h. einen Wert, der zur Kompilierzeit ausgewertet werden kann.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3452 generiert:  
  
```  
// C3452.cpp  
// compile with: /c  
int i;  
[module( name="mod", type=dll, custom={i} ) ];   // C3452  
// try the following line instead  
// [module( name="mod", type=dll, custom={"a"} ) ];  
```
