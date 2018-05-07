---
title: Compilerfehler C3641 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3641
dev_langs:
- C++
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 496ff73822dcc1c886fbd2020f8ec6b8a5a9a2f7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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