---
title: Compilerwarnung C4956 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4956
dev_langs:
- C++
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac369ab3bbdd4afdfb5e8aa555770564f54732de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4956"></a>Compilerwarnung C4956
'typ': Dieser Typ ist nicht überprüfbar  
  
 Diese Warnung wird generiert, wenn [/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) angegeben ist und Ihr Code einen Typ enthält, der nicht überprüfbar ist.  
  
 Weitere Informationen finden Sie unter [reiner und überprüfbarer Code (C + c++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Diese Warnung wird als Fehler ausgegeben. Sie kann mithilfe des [warning](../../preprocessor/warning.md) -Pragmas oder der Compileroption [/wd](../../build/reference/compiler-option-warning-level.md) deaktiviert werden.  
  
 Im folgenden Beispiel wird C4956 generiert:  
  
```  
// C4956.cpp  
// compile with: /clr:safe  
int* p;   // C4956  
```