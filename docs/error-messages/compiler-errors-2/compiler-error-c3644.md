---
title: Compilerfehler C3644 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3644
dev_langs: C++
helpviewer_keywords: C3644
ms.assetid: 2e3f6c41-3ec5-4a01-82bc-f11b61ebe68e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e13d03f7750a5111d9a8058c94bb6736831d2fde
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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