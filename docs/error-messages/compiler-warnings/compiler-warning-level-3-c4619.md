---
title: Compilerwarnung (Stufe 3) C4619 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4619
dev_langs:
- C++
helpviewer_keywords:
- C4619
ms.assetid: 701fea21-01aa-4bea-93d4-1cb8824170b0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd598c99e87947d60831a1d62c268e3b5797b4ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4619"></a>Compilerwarnung (Stufe 3) C4619
\#Pragma-Warnung: Keine Warnungsnummer 'Number' vorhanden ist  
  
 Es wurde versucht, eine Warnung zu deaktivieren, die nicht vorhanden ist.  
  
 Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 Im folgenden Beispiel wird C4619 generiert:  
  
```  
// C4619.cpp  
// compile with: /W3 /c  
#pragma warning(default : 4619)  
#pragma warning(disable : 4354)   // C4619, C4354 does not exist  
```