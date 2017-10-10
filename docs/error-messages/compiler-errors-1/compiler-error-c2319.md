---
title: Compilerfehler C2319 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2319
dev_langs:
- C++
helpviewer_keywords:
- C2319
ms.assetid: 25263e6e-f5ba-4d2c-8727-8c2d8ca2e5ce
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 23db7e68a5f590d7c20f70e122b746b0f43fd2fd
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2319"></a>Compilerfehler C2319
Auf 'try/catch' muss eine zusammengesetzte Anweisung folgen. '{' fehlt  
  
 Es wurde kein `try` - oder `catch` -Block gefunden, der auf die `try` - oder `catch` -Anweisung folgt. Der Block muss in geschweifte Klammern eingeschlossen werden.  
  
 Im folgenden Beispiel wird C2319 generiert:  
  
```  
// C2319.cpp  
// compile with: /EHsc  
#include <eh.h>  
class C {};  
int main() {  
   try {  
      throw "ooops!";  
   }  
   catch( C ) ;    // C2319  
   // try the following line instead  
   // catch( C ) {}  
}  
```
