---
title: Compilerfehler C3389 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3389
dev_langs: C++
helpviewer_keywords: C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 561359afcd9cf694369bd1addb4f641a33a3f989
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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