---
title: Compilerwarnung (Stufe 1 und Stufe 4) C4949 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4949
dev_langs:
- C++
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 241e0295b16ae350cec213bf25b93f7ad72a0808
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

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
