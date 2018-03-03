---
title: Compilerfehler C3389 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3389
dev_langs:
- C++
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bd88753553d2bad1cb9253cfe709e7627c4b01ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3389"></a>Compilerfehler C3389
__declspec(Schlüsselwort) kann nicht verwendet werden, mit/clr: pure oder/clr: safe  
  
 Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
 Ein [__declspec](../../cpp/declspec.md) Modifizierer impliziert einen prozessspezifischen Zustand.  [/ CLR: pure](../../build/reference/clr-common-language-runtime-compilation.md) impliziert einen pro [Appdomain](../../cpp/appdomain.md) Zustand.  Daher Deklarieren einer Variablen mit der `keyword` **__declspec** Modifizierer und die Kompilierung mit **/CLR: pure** ist nicht zulässig.  
  
 Im folgende Beispiel wird C3389 generiert:  
  
```  
// C3389.cpp  
// compile with: /clr:pure /c  
__declspec(dllexport) int g2 = 0;   // C3389  
```