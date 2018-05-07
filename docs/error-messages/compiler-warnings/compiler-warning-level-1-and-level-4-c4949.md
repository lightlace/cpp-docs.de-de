---
title: Compilerwarnung (Stufe 1 und Stufe 4) C4949 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4949
dev_langs:
- C++
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3dbf80f85db7334d4bcb46402851cac601d258f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-and-level-4-c4949"></a>Compilerwarnung (Stufe 1 und Stufe 4) C4949
Pragmas "managed" und "nicht verwaltet" sind sinnvoll, nur beim Kompilieren mit "/ Clr [: Option]"  
  
 Der Compiler ignoriert die [verwaltet](../../preprocessor/managed-unmanaged.md) als auch nicht verwaltete Pragmas, wenn der Quellcode nicht kompiliert wird, mit ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md). Diese Warnung dient nur zu Informationszwecken.  
  
 Im folgenden Beispiel wird C4949 generiert:  
  
```  
// C4949.cpp  
// compile with: /LD /W1  
#pragma managed   // C4949  
```  
  
 Wenn **nicht verwaltete #pragma** wird verwendet, ohne **"/ CLR"**, C4949 wird eine Warnung der Stufe 4.  
  
 Im folgenden Beispiel wird C4949 generiert:  
  
```  
// C4949b.cpp  
// compile with: /LD /W4  
#pragma unmanaged   // C4949  
```