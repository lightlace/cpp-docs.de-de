---
title: Compilerwarnung (Stufe 4) C4238 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4238
dev_langs: C++
helpviewer_keywords: C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8e8e52868d97d31243f92307e9bfd158c818c2f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4238"></a>Compilerwarnung (Stufe 4) C4238
nicht dem Standard entsprechende Erweiterung: Klasse Rvalue als Lvalue verwendet  
  
 Um die Kompatibilität mit früheren Versionen von Visual C++, Microsoft-Erweiterungen (**"/ Ze"**) ermöglichen es Ihnen, einen Klassentyp zu verwenden, wie ein Rvalue-Wert in einem Kontext, implizit oder explizit auf die Adresse akzeptiert. Dies kann in einigen Fällen, wie im folgenden Beispiel gefährlich sein.  
  
## <a name="example"></a>Beispiel  
  
```  
// C4238.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
C * pC = &C();   // C4238  
```  
  
 Diese Art der Verwendung verursacht einen Fehler unter ANSI-Kompatibilität (["/ Za"](../../build/reference/za-ze-disable-language-extensions.md)).