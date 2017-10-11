---
title: Compilerfehler C3626 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3626
dev_langs:
- C++
helpviewer_keywords:
- C3626
ms.assetid: 43926e2b-1ba9-4a43-9343-c58449cbb336
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9acd9c4e08c082d27fbc564031c515ca2a680d30
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3626"></a>Compilerfehler C3626
'Schlüsselwort': '__event'-Schlüsselwort kann nur verwendet werden, auf COM-Schnittstellen, Memberfunktionen und Datenmember, die Zeiger auf Delegaten  
  
 Ein Schlüsselwort wurde falsch verwendet.  
  
 Im folgende Beispiel wird C3626 generiert:  
  
```  
// C3626.cpp  
// compile with: /c  
struct A {  
   __event int i;   // C3626  
// try the following line instead  
// __event int i();  
};  
```
