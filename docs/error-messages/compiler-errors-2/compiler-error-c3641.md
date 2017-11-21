---
title: Compilerfehler C3641 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3641
dev_langs: C++
helpviewer_keywords: C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 992e2a5d34b380146a99f6f78145b022eacd21d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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