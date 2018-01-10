---
title: Compilerwarnung (Stufe 1) C4561 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4561
dev_langs: C++
helpviewer_keywords: C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 03fd67baa07b297ded01e06da37cad2a7cc97c68
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4561"></a>Compilerwarnung (Stufe 1) C4561
"__fastcall" nicht kompatibel mit der "/ Clr" Option: Konvertieren in "\__stdcall"  
  
 Die [__fastcall](../../cpp/fastcall.md) Funktion-Aufrufkonvention nicht verwendet werden, mit der ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) -Compileroption. Der Compiler ignoriert die Aufrufe von `__fastcall`. Um diese Warnung zu beheben, entfernen Sie entweder die Aufrufe von **__fastcall** oder Kompilieren Sie ohne **"/ CLR"**.  
  
 Im folgenden Beispiel wird C4561 generiert:  
  
```  
// C4561.cpp  
// compile with: /clr /W1 /c  
// processor: x86  
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve  
```