---
title: Compilerfehler C2218 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2218
dev_langs:
- C++
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1efda7258616862efc464b493b51ada2c6bd7674
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2218"></a>Compilerfehler C2218
"__vectorcall" kann nicht zusammen mit "/arch:IA32" verwendet werden.  
  
 Die Aufrufkonvention `__vectorcall` wird nur in systemeigenem Code auf x86- und x64-Prozessoren unterstützt, die zusätzlich SIMD-Streamingerweiterungen 2 (SSE2) und höher einschließen. Weitere Informationen finden Sie unter [__vectorcall](../../cpp/vectorcall.md).  
  
 Um diesen Fehler zu beheben, ändern Sie die Compileroptionen in die Befehlssätze Ziel SSE2, AVX oder AVX2. Weitere Informationen finden Sie unter [/arch (x86)](../../build/reference/arch-x86.md).