---
title: Compilerfehler C3641 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3641
dev_langs:
- C++
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 992e2a5d34b380146a99f6f78145b022eacd21d6
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3641"></a>Compilerfehler C3641
'Funktion': ungültige Aufrufkonvention 'Aufrufkonvention' für die Funktion, die mit "/ CLR" kompiliert: pure oder/clr: safe  
  
 Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
 Nur [__clrcall](../../cpp/clrcall.md) Aufrufkonvention kann mit [/CLR: pure](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Im folgende Beispiel wird C3641 generiert:  
  
```  
// C3641.cpp  
// compile with: /clr:pure /c  
void __cdecl f() {}   // C3641  
```
