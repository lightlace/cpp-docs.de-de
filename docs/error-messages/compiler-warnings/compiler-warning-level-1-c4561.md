---
title: Compilerwarnung (Stufe 1) C4561 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4561
dev_langs:
- C++
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4862d7f570faea3e362a505e67bddaf504b32de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33280530"
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