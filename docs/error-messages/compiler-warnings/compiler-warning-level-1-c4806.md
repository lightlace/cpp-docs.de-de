---
title: Compilerwarnung (Stufe 1) C4806 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4806
dev_langs:
- C++
helpviewer_keywords:
- C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92d5b36a653680285523c7cebb605238b37d57c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283392"
---
# <a name="compiler-warning-level-1-c4806"></a>Compilerwarnung (Stufe 1) C4806
"operation": unsichere Operation: kein Wert vom Typ "type" erweitert auf Typ "type" kann mit der angegebenen Konstante übereinstimmen  
  
 Diese Meldung warnt Sie vor Code wie `b == 3`, wobei `b` Typ `bool`aufweist. Aufgrund der Erweiterungsregeln wird `bool` auf `int`erweitert. Dies ist zulässig, es kann aber nie **true**sein. Im folgenden Beispiel wird C4806 generiert:  
  
```  
// C4806.cpp  
// compile with: /W1  
int main()  
{  
   bool b = true;  
   // try..  
   // int b = true;  
  
   if (b == 3)   // C4806  
   {  
      b = false;  
   }  
}  
```