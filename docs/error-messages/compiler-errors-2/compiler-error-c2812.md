---
title: Compilerfehler C2812 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2812
dev_langs: C++
helpviewer_keywords: C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12ab4a753ad2098dfa4c3bccb2190c18bcc2fafb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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