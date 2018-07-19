---
title: Compilerfehler C3644 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3644
dev_langs:
- C++
helpviewer_keywords:
- C3644
ms.assetid: 2e3f6c41-3ec5-4a01-82bc-f11b61ebe68e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a63f191251ecdc53ee082d69b9bbafb9e23b74c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33264943"
---
# <a name="compiler-error-c3644"></a>Compilerfehler C3644
'Funktion': die Funktion zum Generieren von verwalteten Codes kann nicht kompiliert werden.  
  
 Das Vorhandensein einiger Schlüsselwörter in einer Funktion führt dazu, dass die Funktion in systemeigenem Code kompiliert werden.  
  
 Im folgende Beispiel wird C3644 generiert:  
  
```  
// C3644.cpp  
// compile with: /clr  
// processor: x86  
  
void __clrcall Func2(int i) {  
   __asm {}   // C3644  
}  
```