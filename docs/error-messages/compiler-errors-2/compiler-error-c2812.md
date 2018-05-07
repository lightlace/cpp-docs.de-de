---
title: Compilerfehler C2812 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2812
dev_langs:
- C++
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28d46b0f9744f192d677d7b2df27b67e734de1b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2812"></a>Compilerfehler C2812
\#Import wird nicht unterstützt, mit/clr: pure und/CLR: safe  
  
 Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
 [#import-Direktive](../../preprocessor/hash-import-directive-cpp.md) wird nicht unterstützt, mit **/CLR: pure** und **/CLR: safe** da `#import` erfordert die Verwendung eines systemeigenen Compiler-Unterstützung-Bibliotheken.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2812 generiert.  
  
```  
// C2812.cpp  
// compile with: /clr:pure /c  
#import "importlib.tlb"   // C2812  
```