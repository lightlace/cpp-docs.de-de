---
title: Compilerfehler C3862 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3862
dev_langs:
- C++
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: af959252ce5b404d8646ad61e02c5e480b41ed83
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

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
