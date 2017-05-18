---
title: Compilerfehler C3389 | Microsoft-Dokumentation
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
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 6cfe5a03ecbb370eaf290f94ee5e26a5d185a1ae
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3389"></a>Compilerfehler C3389
__declspec(Schlüsselwort) kann nicht verwendet werden, mit/clr: pure oder/clr: safe  
  
 Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 veraltet sind.  
  
 Ein [__declspec](../../cpp/declspec.md) -Modifizierer impliziert einen prozessspezifischen Zustand.  [/ CLR: pure](../../build/reference/clr-common-language-runtime-compilation.md) impliziert eine pro [Appdomain](../../cpp/appdomain.md) Zustand.  Deklaration einer Variablen mit der `keyword` **__declspec** -Modifizierer und die Kompilierung mit **/CLR: pure** ist nicht zulässig.  
  
 Im folgende Beispiel wird C3389 generiert:  
  
```  
// C3389.cpp  
// compile with: /clr:pure /c  
__declspec(dllexport) int g2 = 0;   // C3389  
```
