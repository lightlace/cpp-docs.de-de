---
title: Compilerfehler C3862 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3862
dev_langs: C++
helpviewer_keywords: C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 63fa12348ee2ab58782fad02719918bfe7929ff8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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