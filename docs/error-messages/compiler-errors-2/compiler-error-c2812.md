---
title: Compilerfehler C2812 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2812
dev_langs:
- C++
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 859d371d5886ece416ea6d60c405b114a527864f
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

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
