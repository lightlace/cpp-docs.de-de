---
title: Compilerfehler C3862 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3862
dev_langs:
- C++
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25b0a344eaafedc2f7c0eb60141e3a07fd86c6af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3862"></a>Compilerfehler C3862
'Funktion': kann nicht kompiliert werden eine nicht verwaltete Funktion mit/clr: pure oder/clr: safe  
  
 Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
 Eine Kompilierung mit **/CLR: pure** oder **/CLR: safe** erzeugt eine einzige MSIL-Images, die ein Bild ohne systemeigenen (nicht verwalteten) Code.  Aus diesem Grund können keine der `unmanaged` Pragma in einer **/CLR: pure** oder **/CLR: safe** Kompilierung.  
  
 Weitere Informationen finden Sie unter [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) und [verwaltete, unverwaltete](../../preprocessor/managed-unmanaged.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3862 generiert:  
  
```  
// C3862.cpp  
// compile with: /clr:pure /c  
#pragma unmanaged  
void f() {}   // C3862  
```