---
title: Compilerwarnung (Stufe 1) C4272 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4272
dev_langs: C++
helpviewer_keywords: C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bb34c2a754513e00e593a718499eeea750da3647
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4272"></a>Compilerwarnung (Stufe 1) C4272
'Funktion': RuntimeCompatibility von "__declspec(dllimport)" "; systemeigene Aufrufkonvention muss angegeben werden, beim Importieren einer Funktion.  
  
 Es ist ein Fehler so exportieren Sie eine Funktion mit der [__clrcall](../../cpp/clrcall.md) Aufrufkonvention und der Compiler gibt diese Warnung aus, wenn Sie versuchen, eine Funktion importieren `__clrcall`.  
  
 Im folgenden Beispiel wird C4272 generiert:  
  
```  
// C4272.cpp  
// compile with: /c /W1 /clr  
__declspec(dllimport) void __clrcall Test();   // C4272  
__declspec(dllimport) void Test2();   // OK  
```