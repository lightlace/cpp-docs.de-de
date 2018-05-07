---
title: Compilerwarnung (Stufe 4) C4238 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4238
dev_langs:
- C++
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06dbec01da8d1b47cb7b93c90a22ae5266e9b4c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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