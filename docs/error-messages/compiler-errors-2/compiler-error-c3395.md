---
title: Compilerfehler C3395 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3395
dev_langs:
- C++
helpviewer_keywords:
- C3395
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 202162ecac8907852ca621599f5306884e59ae98
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3395"></a>Compilerfehler C3395
'Funktion': __declspec(dllexport) kann nicht angewendet werden, an eine Funktion mit dem \__clrcall Aufrufkonvention  
  
 `__declspec(dllexport)` und [__clrcall](../../cpp/clrcall.md) sind nicht kompatibel.  Weitere Informationen finden Sie unter [Dllexport, Dllimport](../../cpp/dllexport-dllimport.md).  
  
 Im folgende Beispiel wird C3395 generiert:  
  
```  
// C3395.cpp  
// compile with: /clr /c  
  
__declspec(dllexport) void __clrcall Test(){}   // C3395  
void __clrcall Test2(){}   // OK  
__declspec(dllexport) void Test3(){}   // OK  
```